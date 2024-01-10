<!-- WeatherForCity.svelte -->

<script>
  import { onMount } from "svelte";
  import axios from "axios";

  let weatherData = [];
  let selectedCity = "";
 
  const cities=["Opava","Praha","London","Los Angeles","Ottawa","Bangkok","Jakutsk"]
  const citiesValues=["opava", "praha", "london", "los_angeles", "ottawa", "bangkok", "jakutsk"]

  async function fetchData(){
    try {
      const response = await axios.get(`https://weather-javaspring.azurewebsites.net/weather/${selectedCity}`);
      weatherData = [response.data];
    } catch (error) {
      console.error("Chyba při načítání dat o počasí:", error);
    }
  }

//   onMount(async () => {
//     await fetchData();
//   });
</script>
<h1 class="text-center my-4">Počasí pro vybrané město</h1>
<div class="container">
    <div class="row d-flex justify-content-center">
        <select bind:value={selectedCity} on:change={fetchData} id="city" >
            <option value="" disabled selected hidden>Vyberte město</option>
        {#each cities as city,index}
            <option value={citiesValues[index]}>{city}</option>
        {/each}
        </select>
    </div>
</div>
{#if selectedCity !== "" && weatherData[0]}
<h3 class="my-4">Počasí v {weatherData[0]?.location}</h3>
    <div class="container d-flex justify-content-center">
        <div class="row">         
            <table class="table table-bordered table-dark mb-4" id="all_weather">
                <tbody class="table-body">
                    <tr>
                        <th >Datum a čas</th>
                        <td>{weatherData[0]?.timestamp}</td>
                    </tr>
                    <tr>
                        <th>Teplota</th>
                        <td>{weatherData[0]?.temp_celsius} °C</td>
                    </tr>
                    <tr>
                        <th>Rychlost větru</th>
                        <td>{weatherData[0]?.windSpeed_mps} m/s</td>
                    </tr>
                    <tr>
                        <th>Vlhkost</th>
                        <td>{weatherData[0]?.rel_humidity}%</td>
                    </tr>
                    <tr>
                        <th>Směr větru</th>
                        <td>{weatherData[0]?.wind_direction}</td>
                    </tr>
                    <tr>
                        <th>Popis počasí</th>
                        <td>{weatherData[0]?.weather_description}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div> 
{/if}
<style>
    select{
        width: 50%;
        border-radius: 5px;
    }
    select:focus,select:hover,select:active{
        border: 2px solid black;
    }
    h3{
        padding: 0;
        text-align: center;
    }
    td{
        text-align: center;
    }  
    select{
        box-shadow: 0 0 10px black;
    }  
    option{
        box-shadow: none;
    }  
</style>




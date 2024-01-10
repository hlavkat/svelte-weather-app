<!-- WeatherForAll.svelte -->

<script>
  import { onMount } from "svelte";
  import axios from "axios";

  let weatherData = [];

  onMount(async () => {
    try {
      const response = await axios.get("https://weather-javaspring.azurewebsites.net/weather");
      weatherData = response.data;
    } catch (error) {
      console.error("Chyba při načítání dat o počasí:", error);
    }
  });
</script>
<h1 class="text-center my-4">Počasí pro všechna dostupná města</h1>
<div class="container d-flex justify-content-center">
    <div class="row">
        {#each weatherData as cityData(cityData.location)}
        <div class="col-12 col-lg-3 col-md-4 col-sm-6">
            <table class="table table-bordered table-dark mb-4" id="all_weather">
                <thead>
                    <tr>
                        <td colspan="2" class="text-center"><h5>Počasí v {cityData.location}</h5></td>
                    </tr>
                </thead>
                <tbody class="table-body">
                        <tr>
                            <th >Datum a čas</th>
                            <td>{cityData.timestamp}</td>
                        </tr>
                        <tr>
                            <th>Teplota</th>
                            <td>{cityData.temp_celsius} °C</td>
                        </tr>
                        <tr>
                            <th>Rychlost větru</th>
                            <td>{cityData.windSpeed_mps} m/s</td>
                        </tr>
                        <tr>
                            <th>Vlhkost</th>
                            <td>{cityData.rel_humidity}%</td>
                        </tr>
                        <tr>
                            <th>Směr větru</th>
                            <td>{cityData.wind_direction}</td>
                        </tr>
                        <tr>
                            <th>Popis počasí</th>
                            <td>{cityData.weather_description}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        {/each}         
    </div>
</div> 
<style>
    h5{
        padding: 0;
        text-align: center;
    }
    td{
        text-align: center;
    }

</style>


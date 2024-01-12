<script>
  import { onMount } from 'svelte';

  onMount(() => {
    if (typeof document !== 'undefined') {
      import('../client');
    }
  });
  import img from '$lib/asset/image/pocasi.jpg'
 // import '../../node_modules/bootstrap/js/dist/dropdown'
  //import '../../node_modules/bootstrap/js/dist/collapse'
  </script>
<h1 class="text-center my-5">Moravian Weather</h1>
<div class="container">
  <div>
    <p>Aplikace, která tahá json data z mé jiné aplikace,která je pomocí API stahuje ze serveru <a href="https://www.weatherapi.com"><b>weatherapi</b></a>. Aplikaci s raw json daty můžete otevřít <a href="https://weather-javaspring.azurewebsites.net/weather"><b>zde</b></a>. Kód této aplikace na <a href="https://github.com/hlavkat/weather-app-spring"><b>githubu</b></a>. Pro tuto raw aplikaci jsem si chtěl vyzkoušet svelte kit. Kod této aplikace s basic frontendem <a href="https://github.com/hlavkat/svelte-weather-app"><b>zde</b></a>.</p>
  </div>
  <div class="d-flex justify-content-center">
    <img src={img} alt="" class="img-fluid">
  </div>
</div>
<style>
  @import '../../node_modules/bootstrap/dist/css/bootstrap.css';
  p{
    margin: 10px 50px;
  }
  .container{
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
</style>
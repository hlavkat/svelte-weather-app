<script>
  import { base } from '$app/paths';
</script>
<nav class="navbar navbar-expand-lg bg-dark border-bottom border-body" data-bs-theme="dark">
  <div class="container-fluid">
    <a class="navbar-brand" href={`${base}`}>Moravian Weather</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavDropdown">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href={`${base}`}>Home</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href={`${base}`} role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Počasí
          </a>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href={`${base}/weatherForAll`}>Pro všechna města</a></li>
            <li><a class="dropdown-item" href={`${base}/weatherForCity`}>Pro konkretní město</a></li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</nav>
<slot/>
<script>
  import { onMount } from 'svelte';

  onMount(() => {
    if (typeof document !== 'undefined') {
      import('../client');
    }
  });
</script>
<h1 class="text-center my-5">Moravian Weather</h1>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. A id veniam obcaecati eligendi eaque animi dolor quidem iste odio rerum sit laudantium enim dolorem, tenetur et officiis minus! Maiores voluptates ex et natus aspernatur id necessitatibus illo assumenda rem animi officiis nam, tenetur blanditiis nihil minus tempore odio minima similique veritatis facilis iste delectus beatae. Atque magni nobis soluta accusamus, minima officiis facilis quod earum molestiae quisquam magnam fugiat provident pariatur ratione, maxime, in inventore architecto labore porro! Ipsam ipsa cum repudiandae similique suscipit harum ratione fugit, est, necessitatibus culpa ullam saepe! Assumenda quidem id maxime incidunt mollitia animi odit?</p>
<style>
  @import '../../node_modules/bootstrap/dist/css/bootstrap.css';
  p{
    margin: 10px 50px;
  }
</style>
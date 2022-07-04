<script>
  import UnitTTK from './Unit-TTK.svelte';
  import UnitTG from './Unit-GK.svelte';
  import UnitRoom from './Unit-Room.svelte';

  function changeTemp(ev) {
    console.log('отправка запроса на сервер');
  }
</script>

<main>
  <h1>Контроль температуры</h1>
  <UnitTTK on:changeTemp={changeTemp} />
  <UnitTG on:changeTemp={changeTemp} />
  <UnitRoom on:changeTemp={changeTemp} />
</main>

<style>
  main {
    width: fit-content;
    height: 600px;
    background-color: rgb(68, 64, 64);
    border: 10px solid black;
    border-radius: 10px;
    color: aliceblue;
    text-align: center;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

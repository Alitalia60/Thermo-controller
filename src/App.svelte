<script>
  import UnitTTK from './Unit-TTK.svelte';
  import UnitTG from './Unit-GK.svelte';
  import UnitRoom from './Unit-Room.svelte';
  const optionsGK = {
    minT: 10,
    maxT: 75,
    currentT: 15,
    targetT: 65,
    status: false,
  };
  const optionsTTK = {
    minT: 0,
    maxT: 80,
    currentT: 15,
    targetT: 70,
    status: false,
  };
  const optionsRoom = {
    minT: 10,
    maxT: 22,
    currentT: 15,
    targetT: 1,
    status: false,
  };


  function changeTemp(ev) {
    console.log('отправка запроса на сервер');
  }
</script>

<main>
  <h1>Контроль температуры</h1>
  <!-- <UnitTTK on:changeTemp={changeTemp} options = ''/> -->
  <UnitTTK on:changeTemp={changeTemp} options = ''/>
  <UnitTG on:changeTemp={changeTemp} options=''/>
  <UnitRoom on:changeTemp={changeTemp} options=''/>
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

<script>
  import { createEventDispatcher } from 'svelte';
  export let unitName;
  export let unitId;
  export const params = {
    unitId: '',
    unitName: '',
    minT: 0,
    maxT: 80,
    currentT: 15,
    targetT: 65,
    status: false,
  };

  const dispatch = createEventDispatcher();

  function tempHandle(ev) {
    dispatch('changeTemp', {
      detail: {
        unitId,
        directions: ev.target.classList.contains('tempUp')
          ? 'tempUp'
          : 'tempDown',
      },
    });
  }
</script>

<div class="unit">
  <h3>{unitName}</h3>
  <div class="params">
    <ul>
      <li class="params__item">
        <span>Min t:</span>
        <h5>{params.minT}</h5>
      </li>
      <li class="params__item">
        <span>Max t:</span>
        <h5>{params.maxT}</h5>
      </li>
      <li class="params__item" style="color: white;">
        <span>Current T</span>
        <h5>{params.currentT}</h5>
      </li>
      <li class="params__item">
        <span>Target t</span>
        <h5>{params.targetT}</h5>
      </li>
    </ul>
    <div class="controls">
      <button on:click={tempHandle} class="button tempUp"> + </button>
      <button on:click={tempHandle} class="button tempDown"> - </button>
    </div>
  </div>
</div>

<style>
  h3 {
    color: #ff3e00;
    text-transform: uppercase;
    /* font-size: 4em; */
    font-weight: 100;
    text-align: center;
    margin: 5px;
  }

  .unit {
    width: 400px;
    height: 150px;
    border: 2px solid brown;
    border-radius: 10px;
    background-color: rgb(82, 123, 151);
    margin: 10px;
  }
  .params {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
  .params__item {
    display: inline-block;
  }
  .controls {
    display: flex;
    flex-direction: column;
  }

  .button {
    padding: 0;
    margin: 5px;
    width: 60px;
    height: 30px;
    border-radius: 10px;
    text-align: center;
  }
</style>

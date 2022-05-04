<script lang="ts">
  import type { Writable } from "svelte/store";

  export let text: string;
  export let count: Writable<number>;
  export let totalCount: number = 416;
  $: probability = () => {
    const result = ((32 - $count)/(totalCount)) * 100;
    return result.toFixed(2);
  }
  const sum = () => {
    count.update(n => n + 1);
  }

  const min = () => {
    if ($count > 0) {
      count.update(n => n - 1);
    }
  }

</script>

<div class="card">
  <p class="name">{text}</p>
  <p>{$count}</p>
  <p>{probability()}%</p>
  <div class="button-contaner">
    <button on:click={sum}>+</button>
    <button on:click={min}>-</button>
  </div>
</div>

<style lang="scss">
  .card {
    .name {
      font-size: 20px;
      margin: 0;
    }

    border: solid;
    text-align: center;
    width: 150px;
    margin: 10px 20px;

    .button-contaner {
      margin-bottom: 5px;

      button {
        width: 30px;
      }
    }
  }


</style>

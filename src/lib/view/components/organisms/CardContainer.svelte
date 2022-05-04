<script lang="ts">
  import Card from "../molecules/Card.svelte";
  import type  { Writable } from "svelte/store";
    
  export let ace: Writable<number>;
  export let two: Writable<number>;
  export let three: Writable<number>;
  export let four: Writable<number>;
  export let five: Writable<number>;
  export let six: Writable<number>;
  export let seven: Writable<number>;
  export let eight: Writable<number>;
  export let nine: Writable<number>;
  export let ten: Writable<number>;
  export let jack: Writable<number>;
  export let queen: Writable<number>;
  export let king: Writable<number>;
  export let totalCount: number;

</script>
<div class="card-area">
    <Card text="A" count={ace} {totalCount}></Card>
    <Card text="2" count={two} {totalCount}></Card>
    <Card text="3" count={three} {totalCount}></Card>
    <Card text="4" count={four} {totalCount}></Card>
    <Card text="5" count={five} {totalCount}></Card>
    <Card text="6" count={six} {totalCount}></Card>
    <Card text="7" count={seven} {totalCount}></Card>
    <Card text="8" count={eight} {totalCount}></Card>
    <Card text="9" count={nine} {totalCount}></Card>
    <Card text="10" count={ten} {totalCount}></Card>
    <Card text="J" count={jack} {totalCount}></Card>
    <Card text="Q" count={queen} {totalCount}></Card>
    <Card text="K" count={king} {totalCount}></Card>
</div>

<style lang="scss">
  .card-area {
    margin: 0 auto;
    margin-bottom: 20px;
    display: flex;
    width: 1500px;
    text-align: center;
    justify-content: center;
    flex-wrap: wrap;
  }
</style>

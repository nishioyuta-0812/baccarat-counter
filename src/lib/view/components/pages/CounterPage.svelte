<script lang="ts">
  import CardContainer from "../organisms/CardContainer.svelte";
  import PageTemplate from "../templates/PageTemplate.svelte";
  import { writable } from "svelte/store";
import ProbabilityContainer from "../organisms/ProbabilityContainer.svelte";

  let ace = writable<number>(0);
  let two = writable<number>(0);
  let three = writable<number>(0);
  let four = writable<number>(0);
  let five = writable<number>(0);
  let six = writable<number>(0);
  let seven = writable<number>(0);
  let eight = writable<number>(0);
  let nine = writable<number>(0);
  let ten = writable<number>(0);
  let jack = writable<number>(0);
  let queen = writable<number>(0);
  let king = writable<number>(0);

  $: totalCount = () => {
    const exit = $ace + $two + $three + $four + $five + $six + $seven + $eight + $nine + $ten + $jack + $queen + $king;
    console.log(exit);
    return 416 - exit;
  } 

  const reset = () => {
    ace.set(0);
    two.set(0);
    three.set(0);
    four.set(0);
    five.set(0);
    six.set(0);
    seven.set(0);
    eight.set(0);
    nine.set(0);
    ten.set(0);
    jack.set(0);
    queen.set(0);
    king.set(0);
  }

  $: aceToFour = $ace + $two + $three + $four;
  $: sixToNine = $six + $seven + $eight + $nine;


</script>
<PageTemplate>
  <div class="button-area">
    <button on:click={reset}>Reset</button>
  </div>
  <p class="total">残り　{totalCount()}枚</p>
  <CardContainer {ace} {two} {three} {four} {five} {six} {seven} {eight} {nine} {ten} {jack} {queen} {king} totalCount={totalCount()}></CardContainer>
  <ProbabilityContainer {aceToFour} {sixToNine} totalCount={totalCount()}></ProbabilityContainer>
</PageTemplate>

<style lang="scss">
  .button-area {
    text-align: center;
    margin-bottom: 10px;
  }

  .total {
    text-align: center;
  }
</style>

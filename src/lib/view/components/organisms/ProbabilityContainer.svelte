<script lang="ts">

  export let aceToFour: number;
  export let sixToNine: number;
  export let totalCount: number;


  $: aceToFourProbability = ((128 - aceToFour) / totalCount * 100)  .toFixed(2)
  $: sixToNineProbability = ((128 - sixToNine) / totalCount * 100)  .toFixed(2)
</script>


<div class="probability-container">
<div class="ace-to-four">
  <p>1~4</p>
  <p>{aceToFourProbability}%</p>
</div>
<div class="six-to-nine">
  <p>6~9</p>
  <p>{sixToNineProbability}%</p>
</div>
</div>

<style lang="scss">
  .probability-container {
    display: flex;
    width: 1000px;
    text-align: center;
    justify-content: center;
    margin: 0 auto;

    .ace-to-four {
      text-align: center;
      border: solid;
      width: 200px;
      margin-right: 10px;
    }

    .six-to-nine {
      text-align: center;
      border: solid;
      width: 200px;
      margin-left: 10px;
    }
  }

</style>
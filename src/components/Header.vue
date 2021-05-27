<template>
  <div class="row">
    <h3>Quote Added</h3>
    <div class="col-sm-12">
      <div class="progress">
        <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" :style="{width:(quotesCount/maxQuotes)*100+'%'}">
        {{quotesCount}}/{{maxQuotes}}
        </div>
      </div>
    </div>

  </div>

</template>

<script>
export default {
  name: "Header",
  props:['maxQuotes','quotesCount']
}
</script>

<style scoped>

</style>
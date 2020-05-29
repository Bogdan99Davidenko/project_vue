<template>
  <div class="right_side">
    <div class="choose2">
      <span>Получаете</span>
      <select v-model="convertto">
        <option
          v-bind:key="currencyfrom"
          v-for="currencyfrom in currencyfrom"
          :value="currencyfrom"
        >{{currencyfrom.name}}</option>
      </select>
    </div>
    <div class="sum">
      <span>Сумма</span>
      <input type="number" v-model="final" />
    </div>
  </div>
</template>
<script>
export default {
  props: ["currencyfrom", "final"]
};
</script>
<style>
.right_side {
  display: flex;
  flex-direction: row;
}
.choose2,
.sum {
  display: flex;
  flex-direction: column;
}
.right_side select {
  height: 43px;
  outline: none;
  border-top: none;
  border-left: none;
  border-right: none;
}
.right_side input {
  height: 40px;
  outline: none;
  border-top: none;
  border-left: none;
  border-right: none;
  margin-left: 20px;
}
</style>
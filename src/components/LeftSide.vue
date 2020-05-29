<template>
  <div class="left_side">
    <div class="choose1">
      <span>Отдаете</span>
      <select v-model="convertfrom" @change="setCurrency">
        <option
          v-bind:key="currencyfrom"
          v-for="currencyfrom in currencyfrom"
          :value="currencyfrom"
        >{{currencyfrom.name}}</option>
      </select>
    </div>
    <div class="sum">
      <span>Сумма</span>
      <input type="number" v-model.number="sum" @change="getValue" />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      sum: ""
    };
  },
  props: ["currencyfrom"],
  methods: {
    getValue(sum) {
      this.$emit("getvalue", sum);
    },
    setCurrency(currencyfrom) {
      this.$emit("setcurrency", currencyfrom.name);
    }
  }
};
</script>
<style>
.left_side {
  display: flex;
  flex-direction: row;
}
.left_side select {
  height: 43px;
  outline: none;
  border-top: none;
  border-left: none;
  border-right: none;
}
.left_side input {
  height: 40px;
  outline: none;
  border-top: none;
  border-left: none;
  border-right: none;
  margin-left: 20px;
}
.choose1,
.sum {
  display: flex;
  flex-direction: column;
}
</style>
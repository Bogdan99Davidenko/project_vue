<template>
  <div id="app">
    <Header />
    <h2>Обмен валют</h2>
    <div class="wrapper">
      <Exchange />
      <button id="btn">Обменять</button>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Exchange from "@/components/Exchange";
export default {
  components: {
    Header,
    Exchange
  }
};
</script>

<style>
* {
  margin: 0 auto;
  padding: 0 auto;
}

#app {
  display: flex;
  flex-direction: column;
  font-family: "Ubuntu", sans-serif;
}
h2 {
  margin-top: 120px;
}
.wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
}
#btn {
  margin-top: 100px;
  width: 200px;
  height: 50px;
  font-size: 20px;
  font-family: "Ubuntu", sans-serif;
  border-radius: 5px;
  border: 1px solid rgb(80, 118, 161);
  cursor: pointer;
  outline: none;
}
</style>

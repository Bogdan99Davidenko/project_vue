<template>
  <div class="exchange">
    <LeftSide @setcurrency="setCurrency" @getvalue="getValue" v-bind:currencyfrom="currencyfrom" />
    <button v-on:click="replace">
      <img src="../favicon/favicon-32x32.png" alt />
    </button>
    <RightSide v-bind:currencyfrom="currencyfrom" />
  </div>
</template>
<script>
import LeftSide from "@/components/LeftSide";
import RightSide from "@/components/RightSide";
export default {
  name: "exchange",
  data() {
    return {
      currencyfrom: [
        { name: "EUR", desc: "Euro" },
        { name: "BTC", desc: "Bitcoin" },
        { name: "ETH", desc: "Ethereum" },
        { name: "UAH", desc: "Ukrainian hryvnia" }
      ]
    };
  },
  methods: {
    getValue: function(sum) {
      console.log(sum.target.value);
    },
    setCurrency: function() {
      console.log();
    },
    replace: function() {}
  },
  props: ["convertfrom", "sum"],
  computed: {
    options() {
      return Object.keys(this.currencyfrom).map(c => {
        let o = this.currencyfrom[c];
        return `${o.name}`;
      });
    },
    finalamount: function() {
      var from = this.convertfrom;
      var to = this.convertto;
      var final;
      switch (from) {
        case "EUR":
          if (to == "BTC") {
            final = this.sum.target.value * 0.00012;
          }
          if (to == "ETH") {
            final = this.sum.target.value * 0.0053;
          }
          if (to == "UAH") {
            final = this.sum.target.value * 29.28;
          }
          if (to == "EUR") {
            final = this.sum.target.value;
          }

          break;
        case "BTC":
          if (to == "EUR") {
            final = this.sum.target.value * 8193.15;
          }
          if (to == "ETH") {
            final = this.sum.target.value * 43.51;
          }
          if (to == "UAH") {
            final = this.sum.target.value * 239941.47;
          }
          if (to == "BTC") {
            final = this.sum.target.value;
          }

          break;

        case "ETH":
          if (to == "EUR") {
            final = this.sum.target.value * 188.07;
          }
          if (to == "BTC") {
            final = this.sum.target.value * 0.023;
          }
          if (to == "UAH") {
            final = this.sum.target.value * 5508.1;
          }
          if (to == "ETH") {
            final = this.sum.target.value;
          }

          break;

        case "UAH":
          if (to == "EUR") {
            final = this.sum.target.value * 0.034;
          }
          if (to == "BTC") {
            final = this.sum.target.value * 0.0000042;
          }
          if (to == "ETH") {
            final = this.sum.target.value * 0.00018;
          }
          if (to == "UAH") {
            final = this.sum.target.value;
          }

          break;
      }
      return final;
    }
  },

  components: {
    LeftSide,
    RightSide
  }
};
</script>
<style>
.exchange {
  display: flex;
  flex-direction: row;
  margin-top: 60px;
  width: 60%;
}
.exchange button {
  width: 70px;
  height: 70px;
  border: 1px solid white;
  border-radius: 50%;
  cursor: pointer;
  outline: none;
}
</style>
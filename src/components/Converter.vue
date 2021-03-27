<template>
  <div class="converter">
    <h2>{{ coinA }} para {{ coinB }}</h2>
    <input type="text" v-model="coinA_value" v-bind:placeholder="coinA" />
    <input type="button" value="Converter" v-on:click="convert" />
    <h2>{{ coinB_value }}</h2>
  </div>
</template>

<script>
export default {
  name: "Converter",
  props: ["coinA", "coinB"],

  data() {
    return {
      coinA_value: "",
      coinB_value: 0,
    };
  },

  methods: {
    convert() {
      let from_to = this.coinA + "_" + this.coinB;
      let url = "https://free.currconv.com/api/v7/convert?q=" + from_to + "&apiKey=11f69d6b4cac644066e2";

      fetch(url)
        .then((res) => {
          return res.json();
        })
        .then((json) => {
          let price = json.results[from_to].val;
          this.coinB_value = (price * parseFloat(this.coinA_value)).toFixed(2);
        });
    },
  },
};
</script>

<style scoped>
.converter {
  max-width: 300px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  padding: 20px;
}
input[type="text"] {
  background-color: #eee;
  border-radius: 7px;
  border: 1px solid #a9a9a9;
  padding: 10px;
  margin-right: 10px;
}
input[type="button"] {
  background-color: #6730ec;
  border-radius: 7px;
  padding: 10px;
  border: 1px solid #6730ec;
  color: #fff;
}
input:focus {
  box-shadow: 0 0 0 0;
  border: 2px solid #6730ec;
  outline: 0;
}
</style>
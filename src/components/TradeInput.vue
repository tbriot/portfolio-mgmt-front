<template>
    <div>
        <h1>Enter a trade</h1>
        <b-form inline @submit.prevent="onSubmit" @reset="onReset"> 
            <b-form-select :options="securities" required v-model='form.security'></b-form-select>
            <b-form-select :options="tradeTypes" required v-model='form.tradeType'></b-form-select>
            <b-button type="submit" variant="primary">Add</b-button> 
        </b-form>
    </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        security: null,
        tradeType: "BUY"
      },
      securities: [
        { value: null, text: "Pick one security" },
        { value: "FB", text: "Facebook" },
        { value: "BNS", text: "Bank of Nova Scotia" },
        { value: "TD", text: "Toronto Dominion Bank" }
      ],
      tradeTypes: ["BUY", "SELL"]
    };
  },
  methods: {
    onSubmit(evt) {
      //evt.preventDefault()
      this.$emit('createTradeEvent',  {
        id: 0,
        tradedOn: "1st jan 2000",
        type: this.form.tradeType,
        security: this.form.security
      })
    },
    onReset(evt) {
      console.log("form reset !");
    }
  }
};
</script>

<template>
	<div id="app" class="container">
		<h1>My Portfolio Management App!</h1>
		<TradeInput @createTradeEvent="createTrade"/>
		<TradeList :trades="trades"/>
	</div>
</template>

<script>
import TradeList from "./components/TradeList";
import TradeInput from "./components/TradeInput";

export default {
  data() {
    return {
      trades: tradesSample
    };
  },
  methods: {
    createTrade(trade) {
    this.trades.push(trade);
    }
  },
  components: { TradeList, TradeInput }
};

const tradesSample = [
  {
    id: 1,
    tradedOn: "21 nov 2017",
    type: "Buy",
    security: "FB"
  },
  {
    id: 2,
    tradedOn: "26 nov 2017",
    type: "Buy",
    security: "AAPL"
  },
  {
    id: 3,
    tradedOn: "28 nov 2017",
    type: "Buy",
    security: "GOOG"
  }
];
</script>
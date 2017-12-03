<template>
    <b-table striped hover :items="trades" :caption="'List of trades'"></b-table>
</template>

<<script>
export default {
    props: ['trades']
}
</script>
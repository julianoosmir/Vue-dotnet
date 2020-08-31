<template>
    <div>
        <div :key="r" v-for="r in this.results">{{ r }}</div>
    </div>
</template>
<script>
export default {
        name: 'HelloWorld',
        data() {
            return {
                results: []
            };
        },
        async created() {
            const r = await fetch('/api/values');
            this.results = await r.json();
        }
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

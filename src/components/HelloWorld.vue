<template>
  <div class="hello">
    <div v-for="p in post" :key="p.id">
      {{p}}
    </div>
  </div>
</template>

<script>
  import gql from 'graphql-tag';
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  apollo: {
    post: gql `
    query {
        post (id: 1){
            id
            title
            body
        }
    }
`
  }
}
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

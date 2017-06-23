<template>
  <div class="feed">
    <div v-if="loading === true">
      Chargement des tweets en cours...
    </div>
    <div v-else>
      <ul>
        <li class = "tweet" v-for="tweet in tweets">
          <tweet :tweet="tweet" @retweeted="retweet"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import Tweet from './Tweet'
  export default {
    name: 'feed',
    components: {Tweet},
    props: ['tweets', 'loading']
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: block;
    margin: 0 10px;
  }
  li.tweet:first-child {
   border-top-width: 1px;
  }

  li.tweet {
   border-style: solid;
   border-width: 0 1px 1px 1px;
   border-color: gray;
   width: 500px;
   margin: auto;
  }
  li.button {
   display: inline-block;
  }

  a {
   color: #42b983;
  }

  span.handle {
   color: gray;
  }
  a {
    color: #42b983;
  }
</style>

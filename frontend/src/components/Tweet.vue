<template>
  <div class="tweet">
    <div id="infos_auteurs">
    <strong> {{tweet.auteur.prenom}} {{tweet.auteur.nom}} </strong> <span class="handle"> {{tweet.auteur.handle}} - {{moment(tweet.date).fromNow()
}}  </span>
    </div>
    <div id="contenu">
    {{tweet.contenu}}
    </div>
    <div id="button">
    <ul>
      <li class="button">  <icon name="reply"/> <a @click="retweet()"><icon name="retweet"/> </a>  {{tweet.retweeters.length}} <icon name="heart"/> <icon name="envelope"/></li>
     </ul>
    </div>
  </div>
</template>

<script>
import 'vue-awesome/icons'
import Icon from 'vue-awesome/components/Icon'
import moment from 'moment'
export default {
  created () {
    moment.locale('fr')
  },
  name: 'tweet',
  props: ['tweet'],
  components: {Icon},
  methods: {
    moment: function (date) {
      return moment(date)
    },
    retweet: function () {
      this.$http.get('http://localhost:8080/retweet',
        {
          params: {
            utilisateur: 'audioslave',
            tweet: this.tweet.id
          },
          responseType: 'text'
        },
       resp => {
         console.log('retweeté')
       })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

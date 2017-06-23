<template>
  <div class="tweet">
    <div id="infos_auteurs">
    <strong> {{tweet.auteur.prenom}} {{tweet.auteur.nom}} </strong> <span class="handle"> {{tweet.auteur.handle}} </span>
    </div>
    <div id="contenu">
    {{tweet.contenu}}
    </div>
    <div id="button">
    <ul>
      <li class="button">  <icon name="reply"/> <icon name="retweet"/> <icon name="heart"/> <icon name="envelope"/></li>
     </ul>
    </div>
  </div>
</template>

<script>
import 'vue-awesome/icons'
import Icon from 'vue-awesome/components/Icon'
export default {
  name: 'tweet',
  props: ['tweet'],
  components: {Icon}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

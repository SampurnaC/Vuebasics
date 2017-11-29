<template>
  <div class="article">
    <h1>{{ title }}</h1>
    <p>published on {{ published | moment }}</p>
    <p>Shares: {{ shares }} </p>
    <p class="lead">{{ content }}</p>
    <app-author :author = "author"></app-author>

    <br><br>
    <app-social-sharing @articleWasShared="shared('Hello', $event)"></app-social-sharing>
  </div>
</template>

<script>

  import moment from 'moment';
  import Author from './Author.vue';
  import Social from './Social.vue';

  export default {
    data() {
      return {
        title: '10 reasons why Vue.js is important!',
        published: new Date(),
        content: 'Some summy text',

        author: {
          firstName: 'Sampurna',
          lastName: 'Chapagain'
        },
        shares: 0
      };
    },
    methods: {
      shared: function(event) {
        this.shares++;
        console.log(event)
      }
    },
    filters: {
      moment: function(value){
        return moment(value).format('MMMM Do');
      }
    },

    components: {
      appAuthor: Author,
      appSocialSharing: Social
    }
  }
</script>
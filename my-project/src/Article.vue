<template>
  <div class="article">
    <h1>{{ title }}</h1>
    <p>published on {{ published | moment }}</p>
    <p class="lead">{{ content }}</p>
    <app-author :author = "author"></app-author>
  </div>
</template>

<script>

  import moment from 'moment';
  import Author from './Author.vue';

  export default {
    data() {
      return {
        title: '10 reasons why Vue.js is important!',
        published: new Date(),
        content: 'Some summy text',

        author: {
          firstName: 'Sampurna',
          lastName: 'Chapagain'
        }
      };
    },
    filters: {
      moment: function(value){
        return moment(value).format('MMMM Do');
      }
    },

    components: {
      appAuthor: Author
    }
  }
</script>
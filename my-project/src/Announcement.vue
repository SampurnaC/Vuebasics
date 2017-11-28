<template>
  <div class="alert alert-info">{{ announcement }}</div>
</template>

<script>
  export default {
    data(){
      return {
        announcement: 'The site will go maintenance very sooon !'
      };
    }
  }
</script>
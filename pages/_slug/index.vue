<template>
  <div class="container">
    <div class="main">
    <h1> {{ post.title }}</h1>
        <div class="content">
            <div v-html="post.html"> {{ post.html }}</div>
        </div>
    </div>
</div>
</template>

<script>
import  { getSinglePost } from '~/api/posts';

export default {
  async asyncData ({params}) {
    const post = await getSinglePost( params.slug );
      return { post: post }
    }
  }
</script>

<style lang="scss">
  header{
      height: 15em;
  }

  h1{
      color: white;
      margin-bottom: 1em;
  }

  .content{
      background: white;
      border-radius: 1em;
      padding: 1em;
      margin-bottom: 3em;
  }

  .main{
      margin-top: -9em;
  }
  .content img{
      width: 100%;

  }

  @media only screen and (min-width: 768px){
    .content{
        padding: 2em;
    }
  }

  
</style>

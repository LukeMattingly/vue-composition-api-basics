
<template>
  <div class = "post-detail">
    <h1> This is a post page</h1>
    <p>Disaply content of hte post with Id of {{ $route.params.id }} here!</p>

    <div>
      <button @click="showPostId">
        Show Post ID
      </button>
    </div>
    <div>
      <button @click="goHomeIn3Seconds">
        Go Home in 3 seconds
      </button>
    </div>
    <div>
      <button @click="goToFirstPost">
        Go to first post 
      </button>
    </div>
    <p> <RouterLink to="/posts">&lt;</RouterLink></p>
    <textarea v-autofocus />
  </div>
</template>

<script setup>
import { useRoute, useRouter } from 'vue-router';

const route = useRoute();
const router = useRouter();
  
const showPostId = () => {
  alert(`The post id is ${route.params.id}`);
}

const goHomeIn3Seconds = () => {
  setTimeout(() => {
    router.push('/home');
  }, 3000);
}

  const goToFirstPost = () => {
    router.push({
      name: 'postDetail',
      params: { id: 'id1' }
    });
  }
</script>



<script setup>
import Container from "./Container.vue";
import UserBar from "./UserBar.vue";
import ImageGallery from "./ImageGallery.vue";

</script>

<template>
    <Container>
        <div class="profile-container ">
            <UserBar 
               username="krishna"
               :userInfo="{
                 posts: 4,
                 followers: 100,
                 following: 342
               }"
            />
            <ImageGallery :posts="[{
              id: 1,
              image: 'https://th.bing.com/th/id/OIP.383-9rJ6AFDKMg_G1L_6bQHaF-?w=237&h=191&c=7&r=0&o=5&pid=1.7'
            }, 
            {
              id: 1,
              image: 'https://th.bing.com/th/id/OIP.J6OmGXChgCnnKl2py3rKVgHaHR?rs=1&pid=ImgDetMain'
            }]" />
        </div>
    </Container>
</template>

<style scoped>
  .profile-container {
    display: flex;
    flex-direction: column;
    padding: 20px 0;
  }
</style>
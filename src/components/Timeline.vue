<script setup>
import Container from "./Container.vue";
import Card from "./Card.vue";

const data = [
    {
        id: 1, 
        username: "krishna",
        url: "https://th.bing.com/th/id/OIP.fhDJ8pSa7SraxSWWzzjQeQHaFj?w=241&h=181&c=7&r=0&o=5&pid=1.7",
        caption: "Hare Krishna"
    },
    {
        id: 2, 
        username: "RadhaKrishna",
        url: "https://th.bing.com/th/id/OIP.0rJwb8a-c64DnmzdCaY1MQAAAA?w=164&h=180&c=7&r=0&o=5&pid=1.7",
        caption: "Hare Krishna"
       
    }
]

</script>

<template>
    <Container>
        <div class="timeline-container">
            <Card 
                 v-for="post in data" 
                 :key="post.id" 
                 :post="post" 
            />
        </div>
    </Container>
</template>

<style scoped>
  .timeline-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 0;
  }
</style>
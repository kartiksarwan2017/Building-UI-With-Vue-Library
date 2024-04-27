<script setup>
import { RouterLink } from "vue-router";
import Container from "./Container.vue";
import { ref } from "vue";

const searchUsername = ref("");

const onSearch = () => {

}

</script>

<template>
    <a-layout class="layout">
        <a-layout-header>
            <Container>
                <div class="nav-container">
                    <div class="right-content">
                        <RouterLink to="/">Instagram</RouterLink>
                        <AInputSearch v-model="searchUsername" placeholder="Username..." style="width: 200px"
                            @search="onSearch" />
                    </div>
                    <div class="left-content">
                        <AButton type="primary">Sign Up</AButton>
                        <AButton type="primary">Login</AButton>
                    </div>
                </div>
            </Container>
        </a-layout-header>
    </a-layout>
</template>


<style scoped>
.nav-container {
    display: flex;
    justify-content: space-between;
}

.right-content {
    display: flex;
    align-items: center;
}

.right-content a {
    margin-right: 10px;
}

.left-content button {
    margin-left: 10px;
}
</style>
<script setup>
import { RouterLink, useRouter } from "vue-router";
import Container from "./Container.vue";
import AuthModal from "./AuthModal.vue";
import 'ant-design-vue/dist/reset.css';
import { ref } from "vue";

const router = useRouter();
const searchUsername = ref("");

const onSearch = () => {
    if(searchUsername.value) {
        router.push(`/profile/${searchUsername.value}`);
        searchUsername.value = "";
    }
}
const isAuthenticated = ref(false);

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
                    <div class="left-content" v-if="!isAuthenticated">
                        <AuthModal :isLogin="false" />
                        <AuthModal :isLogin="true" />
                    </div>
                    <div class="left-content" v-else>
                        <a-button type="primary">Profile</a-button>
                        <a-button type="primary">Logout</a-button>
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

.left-content {
    display: flex;
    align-items: center;
}

.left-content button {
    margin-left: 10px;
}

</style>
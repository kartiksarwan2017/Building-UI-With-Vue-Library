<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps(['isLogin']);
const visible = ref(false);
const title = props.isLogin ? 'Login' : 'Signup';
const username = ref("");
const email = ref("");
const password = ref("");

const showModal = () => {
  visible.value = true;
};
const handleOk = (e) => {
  visible.value = false;
};
</script>

<template>
    <div>
        <a-button type="primary" @click="showModal" class="btn">{{title}}</a-button>
        <a-modal :visible="visible" :title="title" @ok="handleOk">
            <a-input class="input" v-if="!isLogin" v-model.lazy="username" placeholder="Username" />
            <a-input class="input" v-model="email" placeholder="Email" />
            <a-input class="input" v-model="password" placeholder="Password" />
        </a-modal>
    </div>
</template>


<style scoped>
  .btn {
    margin-left: 10px;
  }

  .input {
    margin-top: 5px;
  }
</style>


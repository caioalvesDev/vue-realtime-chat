<template>
  <nav>
    <div>
      <h1><strong>Vue</strong> Chat 💬</h1>

      <div v-if="isLogin" class="login">
        <Avatar :src="user.photoURL" />
        <button class="text-gray-400 hover:text-white" @click="signOut">
          Sair
        </button>
      </div>

      <button v-else class="bg-green-500 hover:bg-green-600" @click="signIn">
        Entrar
      </button>
    </div>
  </nav>
</template>

<script>
import Avatar from './Avatar.vue'
import { useAuth } from '../firebase.js'

export default {
  components: { Avatar },
  setup() {
    const { user, isLogin, signOut, signIn } = useAuth()
    return { user, isLogin, signOut, signIn }
  }
}
</script>

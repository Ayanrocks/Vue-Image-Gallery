<template>
    <div class="ui secondary pointing menu">
        <router-link to="/" class="active item">Images Storage</router-link>
    
    <div class="right menu">
        <div v-if="isLoggedIn" class="horizontal">
            <router-link to="/" class="item">Galleries</router-link>
            <router-link to="/upload" class="item" >Upload</router-link>
            <a class="item" @click="logout">Logout</a>
        </div>
        <a v-else href="#" class="ui item right" @click="login">
            Login
        </a>
    </div>

    </div>
</template>



<script>
import { mapActions, mapGetters } from "vuex";

export default {
  name: "AppHeader",
  methods: {
    ...mapActions(["login", "logout"])
  },
  computed: {
    ...mapGetters(["isLoggedIn"])
  }
};
</script>

<style scoped>
.horizontal {
  display: flex;
  flex-direction: row;
}
</style>

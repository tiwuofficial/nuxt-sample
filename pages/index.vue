<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        TIWU
      </h1>
      <h2 class="subtitle">
        My spectacular Nuxt.js project
      </h2>
      <div class="links">
        <span class="button--green" @click="increment">
          Counter {{ count }}
        </span>
        <nuxt-link to="/" class="button--grey">
          Index
        </nuxt-link>
        <nuxt-link to="/about" class="button--grey">
          About
        </nuxt-link>
        <nuxt-link to="/todos" class="button--grey">
          Todo
        </nuxt-link>
        <nuxt-link to="/users/1" class="button--grey">
          User 1
        </nuxt-link>
        <nuxt-link to="/1" class="button--grey">
          Post 1
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  computed: {
    count() {
      return this.$store.state.counter
    }
  },
  methods: {
    ...mapMutations({
      increment: 'increment'
    })
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

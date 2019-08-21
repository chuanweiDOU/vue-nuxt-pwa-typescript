<template>
  <v-app dark>
    <h1 v-if="error.statusCode === 404">
      {{ pageNotFound }}
    </h1>
    <h1 v-else>
      {{ otherError }}
    </h1>
    <NuxtLink to="/">
      Home page
    </NuxtLink>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator';

@Component
class ErrorLayout extends Vue {
  @Prop({ type: Object, default: { } }) error!: { };

  pageNotFound: string = '404 Not Found';
  otherError: string = 'An error occurred';
}

export default ErrorLayout;
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>

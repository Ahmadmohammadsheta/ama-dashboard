
<template>
  <div class="pa-4 ma-4">
    <router-link to="/add">Add</router-link> |
  <NavigationDrawer />
  </div>
</template>

<script>
import NavigationDrawer from '../components/NavigationDrawer.vue'
export default {
    components: {
        NavigationDrawer,
    }
};
</script>
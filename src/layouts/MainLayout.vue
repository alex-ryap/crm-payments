<template>
  <div class="app-main-layout">
    <Navbar @openSidebar="openSidebar = !openSidebar" />
    <Sidebar v-model="openSidebar" />

    <main class="app-content" :class="{ full: !openSidebar }">
      <div class="app-page">
        <router-view />
      </div>
    </main>

    <div class="fixed-action-btn">
      <a class="btn-floating btn-large blue" href="#">
        <i class="large material-icons">add</i>
      </a>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import Sidebar from '@/components/Sidebar.vue';

export default {
  name: 'MainLayout',
  data: () => ({
    openSidebar: true,
  }),
  components: {
    Navbar,
    Sidebar,
  },
};
</script>

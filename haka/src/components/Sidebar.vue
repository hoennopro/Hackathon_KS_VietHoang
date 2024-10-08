<template>
    <div class="sidebar">
        <router-link to="/admin" class="menu-item" :class="{ active: isActive('/admin') }">Dashboard</router-link>
        <router-link to="/admin/manager-user" class="menu-item" :class="{ active: isActive('/admin/manager-user') }">Manager User</router-link>
        <router-link to="/admin/manager-product" class="menu-item" :class="{ active: isActive('/admin/manager-product') }">Manager Product</router-link>
    </div>
</template>

<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();

const isActive = (path) => {
  return route.path === path;
};
</script>

<style scoped>
.sidebar {
    width: 200px;
    background-color: #000;
    height: 100vh;
    color: white;
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    padding-top: 20px;
}

.menu-item {
    padding: 15px 20px;
    text-decoration: none;
    color: white;
}

.menu-item.active,
.menu-item:hover {
    background-color: #333;
}
</style>

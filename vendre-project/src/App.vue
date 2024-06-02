<template>
  <div id="app">
    <NavigationBar />
    <div>
      <h1 class=staff-list>Staff List</h1>
      <StaffList />
    </div>
  </div>
</template>

<script>
import NavigationBar from './components/NavBar.vue';
import StaffList from './components/StaffList.vue';
import './styling/List.css';

export default {
  name: 'App',
  components: {
    NavigationBar,
    StaffList,
  },
};
</script>

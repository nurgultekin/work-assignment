<template>
  <div class="staff-card">
    <img :src="staff.avatar" alt="Profile Picture" class="profile-picture">
    <div class="staff-info">
      <h3 class="staff-name">{{ staff.first_name }} {{ staff.last_name }}</h3>
      <a :href="'mailto:' + staff.email" class="contact-link">{{ staff.email }}</a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    staff: Object
  }
}
</script>

<style src="../styling/List.css" scoped></style>

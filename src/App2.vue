<script>
export default {
  data() {
    return {
      name: "mahdi",
      status: 'other',
      tasks: ['t1', 't2', 't3'],
      link: 'https://google.com'
    }
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') this.status = "pending";
      else if (this.status === 'pending') this.status = "inactive";
      else this.status = "active";
    }
  }
}
</script>

<template>
  <h1>Hello {{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is Pending</p>
  <p v-else>User is Inactive</p>

  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <!-- <a v-bind:href="link">Link</a> -->
  <a :href="link">Link</a>
  <br />
  <!-- <button v-on:click="toggleStatus">Toggle Status</button> -->
  <button @click="toggleStatus">Toggle Status</button>
</template>

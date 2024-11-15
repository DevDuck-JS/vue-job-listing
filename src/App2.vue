<script>
export default {
  data() {
    return {
      name: "John Doe",
      status: "pending",
      tasks: ["Task One", "Task Three"],
      link: "https://google.com",
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === "active") {
        this.status = "pending";
      } else if (this.status === "pending") {
        this.status = "inactive";
      } else {
        this.status = "active";
      }
    },
  },
};
</script>

<template>
  <h1>Vue Job</h1>
  <p>by {{ name }}</p>
  <p v-if="status === 'active'">User is active.</p>
  <p v-else-if="status === 'pending'">User is pending.</p>
  <p v-else>User is inactive</p>

  <h3>Task:</h3>
  <ul>
    <li v-for="task in tasks" :key="tasks">{{ task }}</li>
  </ul>
  <!-- <a v-bind:href="link">Click for Google</a> -->
  <a :href="link">Click for Google</a>

  <!--   <button v-on:click="toggleStatus">Change status</button>
 -->
  <button @click="toggleStatus">Change status</button>
</template>

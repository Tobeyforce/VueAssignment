<template>
    <div class="card">
      <div class="card-body">
        <p class="card-title">Updates</p>
        <ul class="bullet-line-list mt-4">

          <Update :key="update.title" v-for="update of updates" :update="update" />

        </ul>
      </div>
    </div>
</template>

<script>

import Update from "./Update";

export default {
  name: "Updates",
  components: {
    Update
  },
  data() {
    return {
      updates: {}
    };
  },
  created() {
    fetch("https://inlupp-fa.azurewebsites.net/api/updates")
      .then(res => res.json())
      .then(data => {
        this.updates = data;
      });
  }
};
</script>

<style>
</style>
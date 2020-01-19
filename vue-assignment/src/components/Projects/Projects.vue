<template>
  <div class="card">
    <div class="card-body">
      <p class="card-title">Projects</p>
      <div class="d-flex flex-wrap align-items-baseline">
        <h2 id="total-projects-amount" class="mr-3">Projects amount</h2>
        <i class="mdi mdi-arrow-up mr-1 text-success"></i>
        <span>
          <p id="total-projects-growth" class="mb-0 text-success font-weight-medium">Projects growth</p>
        </span>
      </div>
      <p class="mb-0 text-muted">Total users world wide</p>
    </div>
    <canvas id="projects-chart"></canvas>
  </div>
</template>

<script>
export default {
  name: "Projects"
};
</script>

<style>
</style>
<template>
                  <div class="card">
                    <div class="card-body">
                      <p class="card-title">Users</p>
                      <div class="d-flex flex-wrap align-items-baseline">
                        <h2 id="total-user-amount" class="mr-3">User Amount</h2>
                        <i class="mdi mdi-arrow-up mr-1 text-danger"></i>
                        <span>
                          <p id="total-user-growth" class="mb-0 text-danger font-weight-medium">User Growth</p>
                        </span>
                      </div>
                      <p class="mb-0 text-muted">Total users world wide</p>
                    </div>
                    <canvas id="users-chart"></canvas>
                  </div>

</template>

<script>
export default {
    name : "Users"
}
</script>
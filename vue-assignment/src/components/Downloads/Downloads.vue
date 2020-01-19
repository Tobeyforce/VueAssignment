<template>
  <div class="card">
    <div class="card-body">
      <p class="card-title">Downloads</p>
      <p class="text-muted mb-2">
        Watching ice melt. This is fun. Only you could make
        those words cute.
      </p>
      <div class="row mt-4">
        <div class="col-md-6 stretch-card">
          <OfflineDownloads />
        </div>

        <div class="col-md-6 stretch-card mt-4 mt-md-0">
          <OnlineDownloads />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import OfflineDownloads from "./OfflineDownloads";
import OnlineDownloads from "./OnlineDownloads";

export default {
  name: "Downloads",
  components: {
    OfflineDownloads,
    OnlineDownloads
  }
};
</script>
<template>
  <a class="dropdown-item preview-item">
    <div class="preview-thumbnail">
      <div v-bind:class="changeColorClass(notification.title)" class="preview-icon">
        <i v-bind:class="changeImageClass(notification.title)" class="mdi mx-0"></i>
      </div>
    </div>
    <div class="preview-item-content">
      <h6 class="preview-subject font-weight-normal">{{ notification.title }}</h6>
      <p class="font-weight-light small-text mb-0 text-muted">{{ notification.subtitle }}</p>
    </div>
  </a>
</template>

<script>
export default {
  name: "NavBarNotification",
  props: {
    notification: Object
  },
  methods: {
    changeColorClass: title => {
      let className;

      switch (title) {
        case "Application Error":
          className = "bg-success";
          break;
        case "Settings":
          className = "bg-warning";
          break;
        case "New user registration ":
          className = "bg-info";
          break;
          
        default:
          return "badge-success";
      }

      return className;
    },
    changeImageClass: title => {
      let className;

      switch (title) {
        case "Application Error":
          className = "mdi-information";
          break;
        case "Settings":
          className = "mdi-settings";
          break;
        case "New user registration ":
          className = "mdi-account-box";
          break;
          
        default:
          return "mdi-information";
      }

      return className;
    }
  }
}
</script>
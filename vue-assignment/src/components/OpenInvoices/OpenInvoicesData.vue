<template>
  <tr>
    <td>{{ invoice.invoice }}</td>
    <td>{{ invoice.customer }}</td>
    <td>{{ invoice.shipping }}</td>
    <td class="font-weight-bold">{{ invoice.currency }}{{ invoice.bestPrice }}</td>
    <td>{{ invoice.currency }}{{ invoice.purchasedPrice }}</td>
    <td>
      <div class="badge badge-fw" v-bind:class="changeColor(invoice.status)">{{ invoice.status }}</div>
    </td>
  </tr>
</template>

<script>
export default {
  name: "OpenInvoicesData",
  props: {
    invoice: Object
  },
  methods: {
    changeColor: status => {
      let className;

      switch (status) {
        case "Progress":
          className = "badge-success";
          break;
        case "Open":
          className = "badge-warning";
          break;
        case "On hold":
          className = "badge-danger";
          break;

        default:
          return "badge-secondary";
      }

      return className;
    }
  }
};
</script>


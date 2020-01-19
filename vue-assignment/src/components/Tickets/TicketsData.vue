<template>
  <tr>
    <td class="pl-0">
      <div v-bind:class="changeColor(ticket.name)" class="icon-rounded-md">
        <h4 class="font-weight-medium">{{ getInitials(ticket) }}</h4>
      </div>
    </td>
    <td id="one">
      <p class="mb-0">{{ ticket.name}}</p>
      <p class="text-muted mb-0">{{ ticket.city }}</p>
    </td>
    <td>
      <p class="mb-0">{{ splitDateIntoDateTimeArray(ticket)[0] }}</p>
      <p class="text-muted mb-0">{{ splitDateIntoDateTimeArray(ticket)[1] }}</p>
    </td>
    <td>
      <p class="mb-0">{{ ticket.project }}</p>
      <p class="text-muted mb-0">{{ ticket.other }}</p>
    </td>
    <td class="pr-0">
      <i class="mdi mdi-dots-horizontal icon-sm cursor-pointer"></i>
    </td>
  </tr>
</template>

<script>
export default {
  name: "TicketsData",
  props: {
    ticket: Object
  },
  methods: {
    getInitials: ticket => {
      let names = ticket.name.split(" ");
      let initials = names[0][0] + names[1][0];

      return initials;
    },
    splitDateIntoDateTimeArray: ticket => {
      let dateArray = ticket.date.split(",");
      return dateArray;
    },
    changeColor: name => {
      let className;
      switch (name) {
        case "Alta Lucas":
          className = "icon-rounded-primary";
          break;
        case "Teresa Shaw":
          className = "icon-rounded-info";
          break;
        case "Rosa Underwood":
          className = "icon-rounded-danger";
          break;
        case "Vilson Rowa":
          className = "icon-rounded-warning";
          break;

        default:
         className = "icon-rounded-success"
          break;
      }
      return className;
    }
  }
};
</script>
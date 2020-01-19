<template>
    <div class="card">
      <div class="card-body">
        <div class="d-flex justify-content-between align-items-md-end flex-wrap">
          <p class="card-title">Tickets</p>
          <div class="dropdown mb-3 mb-md-0">


              <select v-on:change="changeYear($event.target.value)" id="dropdownMenuDate1" class="btn btn-sm btn-outline-light dropdown-toggle text-dark">

              </select>

          </div>
        </div>
        <div class="table-responsive">
          <table class="table tickets-table mb-2">
            <thead>
              <th class="text-muted pl-0">Name</th>
              <th></th>
              <th class="text-muted">Date</th>
              <th class="text-muted">Projects</th>
            </thead>
            <tbody>


              <TicketsData :key="ticket.name" v-for="ticket of filteredTickets" :ticket="ticket" :initials="initials" />
            </tbody>
          </table>
        </div>
      </div>
    </div>
</template>

<script>
import TicketsData from "./TicketsData";
export default {
  name: "Tickets",
  components: {
    TicketsData
  },
  data() {
    return {
      tickets: [],
      filteredTickets: [],
      year: null,
    };
  },
  methods: {
    
     initialiseTickets: function() {
        fetch('https://inlupp-fa.azurewebsites.net/api/tickets')
        .then(res => res.json())
        .then(data => { 
         this.tickets = data;
            for(let obj of data) {
              this.year = obj.year;
              let element = document.createElement("option");
              element.textContent = obj.year;
              element.value = obj.year;
              element.selected = true;
              document.getElementById('dropdownMenuDate1').appendChild(element);
            }
          this.filterTickets();
        });
      },

      filterTickets: function() {
        for(let obj of this.tickets) {
          if (obj.year == this.year){
            this.filteredTickets = obj.tickets
          }
        }
      },

      changeYear: function(year) {
        this.year = year;
        this.filterTickets();
      },

  },
  created() {

    this.initialiseTickets();
  }
}
</script>
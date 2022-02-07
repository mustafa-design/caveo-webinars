<template>
  <!-- <div class="container mx-auto"> -->
    <FullCalendar :options="calendarOptions" id="calendar" />
  <!-- </div> -->
  <Webinar class="hidden fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-50 shadow-2xl" id="webinar-details" />
</template>

<script>
import FullCalendar from "@fullcalendar/vue3";
import dayGridPlugin from "@fullcalendar/daygrid";
import timeGridPlugin from "@fullcalendar/timegrid";
import listPlugin from "@fullcalendar/list";
import interactionPlugin from "@fullcalendar/interaction";
import Webinar from "../components/Webinar.vue";

export default {
  name: "Home",
  components: { FullCalendar, Webinar },
  data() {
    return {
      // webinars: [],
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin, timeGridPlugin, listPlugin],
        initialView: "dayGridMonth",
        height: 650,
        events: [{}],
        eventClick: this.eventSelect,
      },
    };
  },
  mounted() {
    fetch("http://localhost:3000/webinars")
      .then((res) => res.json())
      .then((data) => (this.calendarOptions.events = data))
      .catch((err) => console.log(err.message));
  },
  methods: {
    eventSelect(event) {
      const popup = document.getElementById('webinar-details')
      const calendar = document.getElementById('calendar')
      console.log(popup)
      popup.classList.remove('hidden')
      calendar.classList.add('opacity-50')
    }
  },
};
</script>

<style>
.fc-event .fc-event-main:hover {
 cursor: pointer
}
</style>

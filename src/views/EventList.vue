<template>
  <h1>Events for good!</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard";
import EventService from "@/services/EventService";

export default {
  name: "EventList",
  components: {
    EventCard,
  },
  data() {
    return {
      events: null,
    };
  },
  created() {
    EventService.getEvents()
      .then((response) => {
        console.log(response);
        this.events = response.data;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.event-card {
  border: 1px solid #000;
  max-width: 400px;
  width: 90vw;
  padding: 20px;
  margin-bottom: 20px;
}
.event-card:hover {
  box-shadow: 0 0 15px 0 rgba(0, 0, 0, 0.3);
}
</style>

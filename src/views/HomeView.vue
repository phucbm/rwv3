<template>
  <div class="events">
    <h1>Events for good!</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard";

export default {
  name: "HomeView",
  components: {
    EventCard,
  },
  data() {
    return {
      events: [
        {
          id: 592101,
          category: "animal welfare",
          title: "Cat Adoption Day",
          description: "Find your new feline friend at this event",
          location: "Meow Town",
          date: "Jan 28, 2022",
          time: "12:00",
          petsAllowed: true,
          organizer: "Kat Lady",
        },
        {
          id: 592101,
          category: "festival",
          title: "Hot Air Balloon Festive",
          description: "Enjoy the arial view with your beloveds",
          location: "Constantinople",
          date: "July 1, 2022",
          time: "16:00",
          petsAllowed: false,
          organizer: "Felix Bui",
        },
      ],
    };
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

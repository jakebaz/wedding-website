<template>
  <DefaultLayout>
    <WelcomeSection />
    <FoodAndDrink />
    <LocationDetails />
    <ContactUs />
    <ScheduleOfEvents />
  </DefaultLayout>
</template>
<script setup>
import DefaultLayout from "@/layouts/DefaultLayout.vue";
import WelcomeSection from "@/views/WelomeSection.vue";
import FoodAndDrink from "@/views/FoodAndDrink.vue";
import LocationDetails from "@/views/LocationDetails.vue";
import ContactUs from "@/views/ContactUs.vue";
import ScheduleOfEvents from "@/views/ScheduleOfEvents.vue";
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville&display=swap");
@import "./scss/variables";
@import "./scss/mixins";
* {
  box-sizing: border-box;
}
html,
body,
#app {
  max-width: 100vw;
  overflow-x: unset;
}
body {
  padding: 0;
  margin: 0;
  font-family: "Libre Baskerville", serif;
  color: $text-primary;
  background: $primary;
}
</style>

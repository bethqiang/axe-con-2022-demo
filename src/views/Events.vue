<template>
  <div class="m-20">
    <h1 class="mb-10">Events</h1>
    <div class="grid grid-cols-2 gap-8">
      <Card
        v-for="event in events"
        :key="event.title"
        class="w-full relative"
      >
        <img :src="event.imgSrc" />
        <h2 class="mt-4">{{ event.title }}</h2>
        <div class="absolute top-0 right-0 bottom-0 left-0 h-full w-full opacity-0 bg-black ease-in duration-200 hover:opacity-100 flex items-center justify-center">
          <LobLink
            :to="event.to"
            variant="primary-button"
            :underline="false"
          >
            View Details
          </LobLink>
        </div>
      </Card>
    </div>
  </div>
</template>

<script>
// "View Details" button is ... sorta? accessible via keyboard but because it's on a hover, it's very confusing where the focus is and what is happening
// use focus instead of hover effects

export default {
  name: 'events-page',
  data () {
    return {
      events: [{
        imgSrc: '/src/assets/images/winter.png',
        title: 'Winter',
        to: '/events/winter'
      },
      {
        imgSrc: '/src/assets/images/spring.png',
        title: 'Spring',
        to: '/events/spring'
      }]
    }
  }
}
</script>

<style>
</style>

<script setup>
import HomeCard from '../components/HomeCard.vue'
</script>

<template>
  <div class="p-8">
    <button type="button" class="text-white text-2xl font-semibold hover:underline cursor-pointer">
      Podcast to start your day
    </button>
    <div class="py-1.5"></div>
    <div class="flex items-center">
      <HomeCard
        image="https://picsum.photos/id/653/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        image="https://picsum.photos/id/30/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        image="https://picsum.photos/id/65/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="md:block hidden"
        image="https://picsum.photos/id/67/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="lg:block hidden"
        image="https://picsum.photos/id/100/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="xl:block hidden"
        image="https://picsum.photos/id/45/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
    </div>
  </div>
  <div class="p-8">
    <button type="button" class="text-white text-2xl font-semibold hover:underline cursor-pointer">
      New Material
    </button>
    <div class="py-1.5"></div>
    <div class="flex items-center">
      <HomeCard
        image="https://picsum.photos/id/653/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        image="https://picsum.photos/id/30/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        image="https://picsum.photos/id/65/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="md:block hidden"
        image="https://picsum.photos/id/67/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="lg:block hidden"
        image="https://picsum.photos/id/100/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="xl:block hidden"
        image="https://picsum.photos/id/45/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
    </div>
  </div>
  <div class="p-8">
    <button type="button" class="text-white text-2xl font-semibold hover:underline cursor-pointer">
      You May Also Like
    </button>
    <div class="py-1.5"></div>
    <div class="flex items-center">
      <HomeCard
        image="https://picsum.photos/id/653/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        image="https://picsum.photos/id/30/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        image="https://picsum.photos/id/65/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="md:block hidden"
        image="https://picsum.photos/id/67/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="lg:block hidden"
        image="https://picsum.photos/id/100/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
      <HomeCard
        class="xl:block hidden"
        image="https://picsum.photos/id/45/300/300"
        title="Sample Title"
        subTitle="Sample Subtitle"
      />
    </div>
  </div>
</template>

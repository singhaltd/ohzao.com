<template>
  <div class="bg-white w-full">
    <div class="group relative">
      <div
        class="
          min-h-65
          aspect-w-1 aspect-h-1
          w-full
          overflow-hidden
          rounded-md
          bg-gray-200
          group-hover:opacity-75
          lg:aspect-none lg:h-65
        "
      >
        <img
          :src="props.thumail ? props.thumail : ''"
          :alt="props.title"
          class="
            h-full
            max-h-[178px]
            min-h-[178px]
            w-full
            object-cover object-center
            lg:h-full lg:w-full
          "
        />
      </div>
      <div class="mt-4 flex justify-between">
        <div>
          <h3 class="text-sm text-gray-700">
            <a href="#">
              <span aria-hidden="true" class="absolute inset-0"></span>
              {{ props.title }}
            </a>
          </h3>
          <p class="mt-1 text-sm text-gray-500">Black</p>
        </div>
        <p class="text-sm font-medium text-gray-900">{{ props.price }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: "",
  },
  thumail: {
    type: String,
    default: "",
  },
  price: {
    type: Number,
    default: 0,
  },
});
</script>

<style>
</style>
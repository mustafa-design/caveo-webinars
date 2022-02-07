<template>
  <div class="container mx-auto pt-10 w-1/2">
    <div class="bg-white shadow overflow-hidden sm:rounded-lg">
      <div class="px-4 py-5 sm:px-6">
        <h3 class="text-lg leading-6 font-medium text-gray-900">
          Webinar Information
        </h3>
        <p class="mt-1 max-w-2xl text-sm text-gray-500">
          Webinar Image
        </p>
        <button
          type="button"
          class="
            inline-flex
            items-center
            p-2
            border border-transparent
            rounded-full
            shadow-sm
            text-white
            bg-indigo-600
            hover:bg-indigo-700
            focus:outline-none
            focus:ring-2
            focus:ring-offset-2
            focus:ring-indigo-500
          "
          @click="hidePopup"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
      <div class="border-t border-gray-200 px-4 py-5 sm:p-0">
        <dl class="sm:divide-y sm:divide-gray-200">
          <div class="py-4 sm:py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6">
            <dt class="text-sm font-medium text-gray-500">title</dt>
            <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">
              {{ webinars.title }}
            </dd>
          </div>
          <div class="py-4 sm:py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6">
            <dt class="text-sm font-medium text-gray-500">Description</dt>
            <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">
              {{ webinars.description }}
            </dd>
          </div>
          <div class="py-4 sm:py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6">
            <dt class="text-sm font-medium text-gray-500">Date &amp; Time</dt>
            <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">
              {{ webinars.date_time }}
            </dd>
          </div>
          <div class="py-4 sm:py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6">
            <dt class="text-sm font-medium text-gray-500">Instructor Name</dt>
            <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">
              {{ webinars.instructor_name }}
            </dd>
          </div>
          <div class="py-4 sm:py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6">
            <dt class="text-sm font-medium text-gray-500">
              Instructor Details
            </dt>
            <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">
              {{ webinars.instructor_details }}
            </dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
const webinars = {
  id: 1,
  image: "",
  title: "title",
  description: "description",
  date_time: "date and time",
  online: true,
  instructor_name: "Instructor name",
  instructor_details: "Instructor details",
  instructor_image: "Instructor image",
};
export default {
  setup() {
    return {
      webinars,
    };
  },
  methods: {
    hidePopup() {
      const popup = document.getElementById("webinar-details");
      const calendar = document.getElementById("calendar");
      popup.classList.add("hidden");
      calendar.classList.remove("opacity-50");
    },
  },
};
</script>

<style>
</style>
<template>
  <div
    class="px-4 xl:px-8 text-light-text dark:text-dark-text bg-light-content dark:bg-dark-content"
  >
    <Head>
      <Title>{{ $t("pages.home.title") }}</Title>
    </Head>
    <h1
      class="pt-6 font-bold transition-all duration-500 responsive-h1 text-light-text dark:text-dark-text"
    >
      {{ $t("pages.home.header") }}
    </h1>
    <div
      class="relative flex flex-col items-start py-4 -mt-2 lg:flex-row lg:items-center space-y-4 lg:mt-0 lg:space-y-0 lg:py-6"
    >
      <h2
        class="transition-all duration-500 responsive-h4 text-light-special-text dark:text-dark-special-text"
      >
        {{ $t("pages.home.subheader") }}
      </h2>
      <TopicMarker topic="My topics dropdown" class="lg:absolute lg:right-0" />
    </div>
    <div class="pb-4 space-y-4">
      <GridHomeMetrics />
      <CardSearchResult
        searchResultType="organization"
        :isPrivate="false"
        :organization="organization"
      />
      <CardSearchResult
        searchResultType="event"
        :isPrivate="false"
        :event="event"
      />
      <CardSearchResult
        searchResultType="resource"
        :isPrivate="false"
        :resource="resource"
      />
      <CardSearchResult
        searchResultType="user"
        :isPrivate="false"
        :user="user"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { Event } from "~~/types/event";
import { Organization } from "~~/types/organization";
import { Resource } from "~~/types/resource";
import { User } from "~~/types/user";
const title = ref("Home");

const { data: organizations } = await useFetch(
  "http://127.0.0.1:8000/organizations"
);

console.log(organizations);

definePageMeta({
  layout: "sidebar",
});
const sidebar = useSidebar();

const resource: Resource = {
  name: "Test Resource",
  organizer: "Testers LLC",
  resourceURL: "www.test.com",
  description: "Test resource :D",
  topic: "Tools",
  relatedLocation: "Berlin",
  creationDate: new Date(),
  stars: 5,
};

const organization: Organization = {
  name: "tech from below",
  location: "Berlin",
  description: "This is the description of tech from below",
  topic: "Technology and Privacy",
  members: 3,
  supporters: 30,
  imageURL: "/images/tech-from-below.svg",
};

const event: Event = {
  name: "Test Event",
  type: "act",
  tagline: "We love to test!",
  organizer: "Testers LLC",
  topic: "Testing and Designing",
  description: "This is a test event for testers.",
  getInvolvedDescription: "Wanna help test?",
  onlineLocation: "Zoom Test Room",
  date: new Date(),
  supporters: 10,
};

const user: User = {
  name: "John A. Tester",
  location: "Testville, TN",
  supporters: 123,
  description: "I love to test!",
};
</script>

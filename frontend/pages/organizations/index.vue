<template>
  <div
    class="px-8 text-light-text dark:text-dark-text bg-light-content dark:bg-dark-content"
  >
    <Head>
      <Title>{{ $t("pages.organizations.index.title") }}</Title>
    </Head>
    <PageBreadcrumbs class="mt-4" />
    <h1
      class="pt-6 font-bold transition-all duration-500 responsive-h1 text-light-text dark:text-dark-text"
    >
      {{ $t("pages.organizations.index.header") }}
    </h1>
    <flex class="relative flex items-center py-6"
      ><h2
        class="transition-all duration-500 responsive-h4 text-light-special-text dark:text-dark-special-text"
      >
        {{ $t("pages.organizations.index.subheader") }}
      </h2>
      <TopicMarker topic="My topics dropdown" class="absolute right-7" />
    </flex>
    <div class="pb-4 space-y-4">
      <CardSearchResult
        searchResultType="organization"
        :isPrivate="false"
        :organization="organization"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { Organization } from "~~/types/organization";

definePageMeta({
  layout: "sidebar",
});
const sidebar = useSidebar();

const organization: Organization = {
  name: "tech from below",
  location: "Berlin",
  description: "This is the description of tech from below",
  topic: "Technology and Privacy",
  members: 3,
  supporters: 30,
  imageURL: "/images/tech-from-below.svg",
};
</script>

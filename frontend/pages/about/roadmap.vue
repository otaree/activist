<template>
  <div
    class="text-light-text dark:text-dark-text bg-light-content dark:bg-dark-content"
  >
    <Head>
      <Title>{{ $t("pages.about.roadmap.title") }}</Title>
    </Head>
    <div
      class="flex flex-col items-center w-full responsive-py-4 responsive-px-5"
    >
      <!-- Note: image on top of content. -->
      <img
        v-if="$colorMode.value == 'light'"
        src="/images/content_pages/icons/arcticons_bike_location_light.png"
        alt="A bicycle within a balloon-shaped icon."
        class="h-40 mb-4 md:hidden sm:h-52"
      />
      <img
        v-else-if="$colorMode.value == 'dark'"
        src="/images/content_pages/icons/arcticons_bike_location_dark.png"
        alt="A bicycle within a balloon-shaped icon."
        class="h-40 mb-4 md:hidden sm:h-52"
      />
      <div class="w-10/12 grid grid-cols-1 md:w-full 2xl:grid-cols-2">
        <div class="items-center text-left space-y-4 md:items-start">
          <!-- Note: image floating right of content. -->
          <img
            v-if="$colorMode.value == 'light'"
            src="/images/content_pages/icons/arcticons_bike_location_light.png"
            alt="A bicycle within a balloon-shaped icon."
            class="hidden float-right h-64 p-4 md:block 2xl:hidden lg:h-72"
          />
          <img
            v-else-if="$colorMode.value == 'dark'"
            src="/images/content_pages/icons/arcticons_bike_location_dark.png"
            alt="A bicycle within a balloon-shaped icon."
            class="hidden float-right h-64 p-4 md:block 2xl:hidden lg:h-72"
          />
          <h1 class="pb-2 font-bold responsive-h1">Roadmap</h1>
          <div class="flex flex-row py-2 space-x-3">
            <Icon
              name="bi:info-circle-fill"
              size="1.25em"
              class="text-light-link-text dark:text-dark-link-text mt-[0.125rem]"
            />
            <p>
              {{ $t("pages.about.roadmap.subheader-pt-1") }}
              <a
                href="https://github.com/activist-org/activist"
                class="items-center focus-brand link-text"
                target="_blank"
              >
                {{ $t("pages.about.roadmap.subheader-pt-2") }}
                <Icon
                  name="bi:box-arrow-up-right"
                  size="1em"
                  style="vertical-align: baseline"
                />
              </a>
              {{ $t("pages.about.roadmap.subheader-pt-3") }}
            </p>
          </div>
          <p>
            {{ $t("pages.about.roadmap.section-1-paragraph-1") }}
          </p>
          <p class="pb-2 lg:pb-4">
            {{ $t("pages.about.roadmap.section-1-paragraph-2-pt-1") }}
            <a
              href="https://github.com/orgs/activist-org/projects/1"
              class="items-center focus-brand link-text"
              target="_blank"
            >
              {{ $t("pages.about.roadmap.section-1-paragraph-2-pt-2") }}
              <Icon
                name="bi:box-arrow-up-right"
                size="1em"
                style="vertical-align: baseline"
              />
            </a>
            {{ $t("pages.about.roadmap.section-1-paragraph-2-pt-3") }}
            <a
              href="https://matrix.to/#/#activist_community:matrix.org"
              class="items-center focus-brand link-text"
              target="_blank"
            >
              {{ $t("pages.about.roadmap.section-1-paragraph-2-pt-4") }}
              <Icon
                name="bi:box-arrow-up-right"
                size="1em"
                style="vertical-align: baseline"
              />
            </a>
            {{ $t("pages.about.roadmap.section-1-paragraph-2-pt-5") }}
          </p>
          <div
            class="flex flex-col items-center space-y-2 md:items-left sm:space-x-4 sm:space-y-0 sm:flex-row"
          >
            <BtnLabeled
              :cta="true"
              :label="$t('components.btn-labeled.suggest-a-feature')"
              linkTo="https://github.com/activist-org/activist/issues"
              fontSize="lg"
            />
            <BtnLabeled
              :cta="false"
              :label="$t('components.btn-labeled.return-home')"
              linkTo="/"
              fontSize="lg"
            />
          </div>
        </div>
        <div class="flex justify-end pr-32">
          <!-- Note: image right of content. -->
          <img
            v-if="$colorMode.value == 'light'"
            src="/images/content_pages/icons/arcticons_bike_location_light.png"
            alt="A bicycle within a balloon-shaped icon."
            class="hidden 2xl:block h-80"
          />
          <img
            v-else-if="$colorMode.value == 'dark'"
            src="/images/content_pages/icons/arcticons_bike_location_dark.png"
            alt="A bicycle within a balloon-shaped icon."
            class="hidden 2xl:block h-80"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

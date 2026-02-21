<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryCollection('index').first())

useSeoMeta({
  titleTemplate: '',
  title: 'Sumio - Your AI Email Digest on Telegram',
  ogTitle: 'Sumio - Your AI Email Digest on Telegram',
  description: 'Sumio reads your emails and sends you one clean, intelligent daily digest on Telegram. Only what matters, nothing else.',
  ogDescription: 'Sumio reads your emails and sends you one clean, intelligent daily digest on Telegram. Only what matters, nothing else.'
})
</script>

<template>
  <div>
    <SumioHero />

    <div v-if="page">
      <UPageSection
        v-for="(section, index) in page.sections"
        :key="index"
        :title="section.title"
        :description="section.description"
        :orientation="section.orientation"
        :reverse="section.reverse"
        :features="section.features"
      >
        <ImagePlaceholder />
      </UPageSection>

      <UPageSection
        :title="page.features.title"
        :description="page.features.description"
      >
        <UPageGrid>
          <UPageCard
            v-for="(item, index) in page.features.items"
            :key="index"
            v-bind="item"
            spotlight
          />
        </UPageGrid>
      </UPageSection>

      <UPageSection
        id="testimonials"
        :headline="page.testimonials.headline"
        :title="page.testimonials.title"
        :description="page.testimonials.description"
      >
        <UPageColumns class="xl:columns-4">
          <UPageCard
            v-for="(testimonial, index) in page.testimonials.items"
            :key="index"
            variant="subtle"
            :description="testimonial.quote"
            :ui="{ description: 'before:content-[open-quote] after:content-[close-quote]' }"
          >
            <template #footer>
              <UUser
                v-bind="testimonial.user"
                size="lg"
              />
            </template>
          </UPageCard>
        </UPageColumns>
      </UPageSection>

      <USeparator />

      <UPageCTA
        v-bind="page.cta"
        variant="naked"
        class="overflow-hidden"
      >
        <LazyStarsBg />
      </UPageCTA>
    </div>
  </div>
</template>

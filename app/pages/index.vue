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
      <!-- Alternating section backgrounds -->
      <div
        v-for="(section, index) in page.sections"
        :key="index"
        :class="index % 2 === 0 ? 'bg-[var(--color-brand-surface)]' : 'bg-[var(--color-brand-surface-alt)]'"
      >
        <UPageSection
          :title="section.title"
          :description="section.description"
          :orientation="section.orientation"
          :reverse="section.reverse"
          :features="section.features"
          :ui="{
            title: 'text-white',
            description: 'text-slate-400',
            featureIcon: 'text-[var(--color-brand-cyan)]'
          }"
        >
          <ImagePlaceholder />
        </UPageSection>
      </div>

      <!-- Features grid section -->
      <div class="bg-[var(--color-brand-deep)]">
        <UPageSection
          :title="page.features.title"
          :description="page.features.description"
          :ui="{
            title: 'text-white',
            description: 'text-slate-400'
          }"
        >
          <UPageGrid>
            <UPageCard
              v-for="(item, idx) in page.features.items"
              :key="idx"
              v-bind="item"
              spotlight
              :ui="{
                icon: 'text-[var(--color-brand-cyan)]',
                title: 'text-white',
                description: 'text-slate-400',
                root: 'bg-[var(--color-brand-surface)] border-[var(--color-brand-blue)]/20 hover:border-[var(--color-brand-cyan)]/30 transition-colors duration-300'
              }"
            />
          </UPageGrid>
        </UPageSection>
      </div>

      <!-- Testimonials section -->
      <div class="bg-[var(--color-brand-surface-alt)]">
        <UPageSection
          id="testimonials"
          :headline="page.testimonials.headline"
          :title="page.testimonials.title"
          :description="page.testimonials.description"
          :ui="{
            headline: 'text-[var(--color-brand-cyan)]',
            title: 'text-white',
            description: 'text-slate-400'
          }"
        >
          <UPageColumns class="xl:columns-4">
            <UPageCard
              v-for="(testimonial, idx) in page.testimonials.items"
              :key="idx"
              variant="subtle"
              :description="testimonial.quote"
              :ui="{
                description: 'before:content-[open-quote] after:content-[close-quote] text-slate-300',
                root: 'bg-[var(--color-brand-surface)] border-[var(--color-brand-blue)]/15'
              }"
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
      </div>

      <div class="bg-[var(--color-brand-deep)]">
        <USeparator />
      </div>

      <!-- CTA section -->
      <div class="bg-[var(--color-brand-deep)]">
        <UPageCTA
          :title="page.cta.title"
          :description="page.cta.description"
          :links="page.cta.links"
          variant="naked"
          class="overflow-hidden"
          :ui="{
            title: 'text-white',
            description: 'text-slate-400'
          }"
        >
          <LazyStarsBg />
        </UPageCTA>
      </div>
    </div>
  </div>
</template>

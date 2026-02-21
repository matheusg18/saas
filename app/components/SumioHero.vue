<template>
  <section class="relative overflow-hidden">
    <HeroBackground />

    <UContainer class="relative py-24 sm:py-32 lg:py-40">
      <div class="flex flex-col lg:flex-row items-center gap-12 lg:gap-16">
        <!-- Left: Copy -->
        <div class="flex flex-col items-center lg:items-start text-center lg:text-left flex-1 max-w-2xl">
          <UBadge
            label="AI-powered email intelligence"
            variant="subtle"
            size="md"
            class="mb-6"
          />

          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight text-[var(--ui-text)] text-balance">
            Your inbox is
            <span class="text-primary">overwhelming.</span>
            <br>
            We fix that.
          </h1>

          <p class="mt-6 text-lg sm:text-xl leading-relaxed text-[var(--ui-text-muted)] max-w-xl text-pretty">
            Sumio reads your emails and sends you one clean, intelligent daily digest on Telegram. Only what matters, nothing else.
          </p>

          <div class="flex flex-col sm:flex-row items-center gap-3 mt-10">
            <UButton
              label="Start for free"
              size="xl"
              trailing-icon="i-lucide-arrow-right"
              to="/signup"
            />
            <UButton
              label="See how it works"
              size="xl"
              color="neutral"
              variant="subtle"
              icon="i-lucide-play"
              to="#how-it-works"
            />
          </div>

          <p class="mt-5 text-sm text-[var(--ui-text-dimmed)] flex items-center gap-1.5">
            <UIcon
              name="i-lucide-shield-check"
              class="text-emerald-500"
            />
            No credit card required. Your emails stay private.
          </p>
        </div>

        <!-- Right: Telegram mockup -->
        <div class="flex-1 w-full max-w-md lg:max-w-sm">
          <div class="relative">
            <!-- Decorative glow behind mockup -->
            <div
              class="absolute -inset-4 bg-[var(--ui-color-primary-500)]/5 rounded-3xl blur-2xl"
              aria-hidden="true"
            />
            <TelegramMockup class="relative" />
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>

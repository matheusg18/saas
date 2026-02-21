<template>
  <section class="relative overflow-hidden bg-[var(--color-brand-deep)]">
    <HeroBackground />

    <UContainer class="relative py-24 sm:py-32 lg:py-40">
      <div class="flex flex-col lg:flex-row items-center gap-12 lg:gap-16">
        <!-- Left: Copy -->
        <div class="flex flex-col items-center lg:items-start text-center lg:text-left flex-1 max-w-2xl">
          <span
            class="inline-flex items-center gap-1.5 rounded-full border border-[var(--color-brand-cyan-muted)] bg-[var(--color-brand-cyan)]/5 px-3.5 py-1.5 text-xs font-medium text-[var(--color-brand-cyan)] mb-6"
          >
            <UIcon
              name="i-lucide-sparkles"
              class="text-sm"
            />
            AI-powered email intelligence
          </span>

          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight text-white text-balance">
            Your inbox is
            <span class="text-[var(--color-brand-cyan)]">overwhelming.</span>
            <br>
            We fix that.
          </h1>

          <p class="mt-6 text-lg sm:text-xl leading-relaxed text-slate-400 max-w-xl text-pretty">
            Sumio reads your emails and sends you one clean, intelligent daily digest on Telegram. Only what matters, nothing else.
          </p>

          <div class="flex flex-col sm:flex-row items-center gap-3 mt-10">
            <UButton
              label="Start for free"
              size="xl"
              trailing-icon="i-lucide-arrow-right"
              to="/signup"
              :ui="{
                base: 'bg-[var(--color-brand-amber)] hover:bg-[var(--color-brand-amber-hover)] text-[var(--color-brand-deep)] font-semibold shadow-lg shadow-[var(--color-brand-amber)]/20 transition-all duration-200 border-0 ring-0 focus-visible:ring-2 focus-visible:ring-[var(--color-brand-amber)]'
              }"
            />
            <button
              class="inline-flex items-center gap-2 rounded-lg border border-[var(--color-brand-cyan)]/40 bg-transparent px-5 py-3 text-base font-semibold text-[var(--color-brand-cyan)] transition-all duration-200 hover:bg-[var(--color-brand-cyan)]/10 hover:border-[var(--color-brand-cyan)]/70 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-[var(--color-brand-cyan)]"
              @click="$router.push('#how-it-works')"
            >
              <UIcon
                name="i-lucide-play"
                class="text-lg"
              />
              See how it works
            </button>
          </div>

          <p class="mt-5 text-sm text-slate-500 flex items-center gap-1.5">
            <UIcon
              name="i-lucide-shield-check"
              class="text-emerald-400"
            />
            No credit card required. Your emails stay private.
          </p>
        </div>

        <!-- Right: Telegram mockup -->
        <div class="flex-1 w-full max-w-md lg:max-w-sm">
          <div class="relative">
            <!-- Decorative radial glow behind mockup -->
            <div
              class="absolute -inset-12 rounded-full blur-3xl opacity-30"
              style="background: radial-gradient(circle, var(--color-brand-cyan) 0%, var(--color-brand-blue) 50%, transparent 70%);"
              aria-hidden="true"
            />
            <!-- Secondary amber glow accent -->
            <div
              class="absolute -bottom-8 -right-8 w-40 h-40 rounded-full blur-3xl opacity-15"
              style="background: radial-gradient(circle, var(--color-brand-amber) 0%, transparent 70%);"
              aria-hidden="true"
            />
            <TelegramMockup class="relative" />
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>

<script setup lang="ts">
const currentTime = computed(() => {
  const now = new Date()
  const hours = now.getHours().toString().padStart(2, '0')
  const minutes = now.getMinutes().toString().padStart(2, '0')
  return `${hours}:${minutes}`
})
</script>

<template>
  <div class="w-full max-w-sm mx-auto">
    <div class="rounded-2xl border border-[var(--ui-border)] bg-[var(--ui-bg)] shadow-xl overflow-hidden">
      <!-- Telegram header -->
      <div class="flex items-center gap-3 px-4 py-3 border-b border-[var(--ui-border)] bg-[var(--ui-bg-muted)]">
        <div class="flex items-center justify-center w-9 h-9 rounded-full bg-[var(--ui-color-primary-500)] shrink-0">
          <UIcon
            name="i-lucide-bot"
            class="text-white text-lg"
          />
        </div>
        <div class="flex flex-col">
          <span class="text-sm font-semibold text-[var(--ui-text)]">Sumio</span>
          <span class="text-xs text-[var(--ui-text-muted)]">bot</span>
        </div>
      </div>

      <!-- Chat area -->
      <div class="flex flex-col gap-3 p-4">
        <!-- Bot message bubble -->
        <div class="flex flex-col gap-2 max-w-[85%]">
          <div class="rounded-2xl rounded-tl-sm bg-[var(--ui-bg-elevated)] border border-[var(--ui-border)] px-4 py-3">
            <p class="text-xs font-semibold text-[var(--ui-color-primary-500)] mb-2">
              Your Daily Digest
            </p>

            <div class="flex flex-col gap-2.5">
              <!-- Email item 1 -->
              <div class="flex items-start gap-2">
                <div class="mt-0.5 shrink-0">
                  <UIcon
                    name="i-lucide-alert-circle"
                    class="text-red-500 text-sm"
                  />
                </div>
                <div>
                  <p class="text-xs font-medium text-[var(--ui-text)]">
                    AWS billing alert
                  </p>
                  <p class="text-[11px] leading-relaxed text-[var(--ui-text-muted)]">
                    Usage exceeded $150 threshold on us-east-1
                  </p>
                </div>
              </div>

              <!-- Email item 2 -->
              <div class="flex items-start gap-2">
                <div class="mt-0.5 shrink-0">
                  <UIcon
                    name="i-lucide-users"
                    class="text-[var(--ui-color-primary-500)] text-sm"
                  />
                </div>
                <div>
                  <p class="text-xs font-medium text-[var(--ui-text)]">
                    Team standup notes
                  </p>
                  <p class="text-[11px] leading-relaxed text-[var(--ui-text-muted)]">
                    3 blockers flagged, deployment moved to Friday
                  </p>
                </div>
              </div>

              <!-- Email item 3 -->
              <div class="flex items-start gap-2">
                <div class="mt-0.5 shrink-0">
                  <UIcon
                    name="i-lucide-calendar"
                    class="text-emerald-500 text-sm"
                  />
                </div>
                <div>
                  <p class="text-xs font-medium text-[var(--ui-text)]">
                    Client meeting confirmed
                  </p>
                  <p class="text-[11px] leading-relaxed text-[var(--ui-text-muted)]">
                    Tomorrow at 2pm with Acme Corp
                  </p>
                </div>
              </div>

              <USeparator class="my-0.5" />

              <!-- Summary -->
              <p class="text-[11px] leading-relaxed text-[var(--ui-text-muted)]">
                <span class="font-medium text-[var(--ui-text)]">+12 more emails</span> processed. Nothing else needs your attention right now.
              </p>
            </div>

            <p class="text-[10px] text-[var(--ui-text-dimmed)] text-right mt-2">
              {{ currentTime }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

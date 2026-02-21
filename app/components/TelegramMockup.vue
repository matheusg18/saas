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
    <div class="rounded-2xl border border-[var(--color-brand-blue)]/40 bg-[var(--color-brand-surface)] shadow-2xl shadow-black/40 overflow-hidden">
      <!-- Telegram header -->
      <div class="flex items-center gap-3 px-4 py-3 border-b border-[var(--color-brand-blue)]/30 bg-[var(--color-brand-surface-alt)]">
        <div class="flex items-center justify-center w-9 h-9 rounded-full bg-[var(--color-brand-cyan)] shrink-0">
          <UIcon
            name="i-lucide-bot"
            class="text-[var(--color-brand-deep)] text-lg"
          />
        </div>
        <div class="flex flex-col">
          <span class="text-sm font-semibold text-white">Sumio</span>
          <span class="text-xs text-slate-400">bot</span>
        </div>
      </div>

      <!-- Chat area -->
      <div class="flex flex-col gap-3 p-4">
        <!-- Bot message bubble -->
        <div class="flex flex-col gap-2 max-w-[85%]">
          <div class="rounded-2xl rounded-tl-sm bg-[var(--color-brand-surface-alt)] border border-[var(--color-brand-blue)]/25 px-4 py-3">
            <p class="text-xs font-semibold text-[var(--color-brand-cyan)] mb-2">
              Your Daily Digest
            </p>

            <div class="flex flex-col gap-2.5">
              <!-- Email item 1 -->
              <div class="flex items-start gap-2">
                <div class="mt-0.5 shrink-0">
                  <UIcon
                    name="i-lucide-alert-circle"
                    class="text-[var(--color-brand-amber)] text-sm"
                  />
                </div>
                <div>
                  <p class="text-xs font-medium text-white">
                    AWS billing alert
                  </p>
                  <p class="text-[11px] leading-relaxed text-slate-400">
                    Usage exceeded $150 threshold on us-east-1
                  </p>
                </div>
              </div>

              <!-- Email item 2 -->
              <div class="flex items-start gap-2">
                <div class="mt-0.5 shrink-0">
                  <UIcon
                    name="i-lucide-users"
                    class="text-[var(--color-brand-cyan)] text-sm"
                  />
                </div>
                <div>
                  <p class="text-xs font-medium text-white">
                    Team standup notes
                  </p>
                  <p class="text-[11px] leading-relaxed text-slate-400">
                    3 blockers flagged, deployment moved to Friday
                  </p>
                </div>
              </div>

              <!-- Email item 3 -->
              <div class="flex items-start gap-2">
                <div class="mt-0.5 shrink-0">
                  <UIcon
                    name="i-lucide-calendar"
                    class="text-emerald-400 text-sm"
                  />
                </div>
                <div>
                  <p class="text-xs font-medium text-white">
                    Client meeting confirmed
                  </p>
                  <p class="text-[11px] leading-relaxed text-slate-400">
                    Tomorrow at 2pm with Acme Corp
                  </p>
                </div>
              </div>

              <div class="border-t border-[var(--color-brand-blue)]/20 my-0.5" />

              <!-- Summary -->
              <p class="text-[11px] leading-relaxed text-slate-400">
                <span class="font-medium text-white">+12 more emails</span> processed. Nothing else needs your attention right now.
              </p>
            </div>

            <p class="text-[10px] text-slate-500 text-right mt-2">
              {{ currentTime }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

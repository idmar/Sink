<script setup lang="ts">
import { GitHubIcon } from 'vue3-simple-icons'

const title = 'Lynk'
const github = 'https://github.com/idmar'
</script>

<template>
  <div
    class="
      flex min-h-svh flex-col overflow-x-clip bg-background text-foreground
    "
  >
    <Button
      as-child variant="secondary" class="
        fixed top-4 left-4 z-50 -translate-y-24
        focus-within:translate-y-0
      "
    >
      <a href="#main-content">{{ $t('layouts.links.skip_to_content') }}</a>
    </Button>
    <header class="border-b pt-[env(safe-area-inset-top)]">
      <div
        class="
          mx-auto flex max-w-6xl items-center justify-between gap-4 px-6 py-4
        "
      >
        <NuxtLink
          to="/" :title="title" :aria-label="$t('layouts.links.home_aria_label')" class="
            flex items-center space-x-2
          "
        >
          <span class="flex size-8 items-center justify-center rounded-full">
            <img
              src="/sink.png" :alt="`${title} Logo`" width="32" height="32" class="
                size-full rounded-full
              "
            >
          </span>
          <span class="text-xl font-black">{{ title }}</span>
        </NuxtLink>
        <div class="flex items-center gap-2">
          <SwitchLanguage />
          <SwitchTheme />
        </div>
      </div>
    </header>
    <main id="main-content" class="flex flex-1 flex-col">
      <slot />
    </main>
    <footer class="border-t pt-6 pb-[calc(1.5rem+env(safe-area-inset-bottom))]">
      <div
        class="mx-auto flex max-w-6xl items-center justify-between gap-4 px-6"
      >
        <NuxtLink
          to="/" :title="title" :aria-label="$t('layouts.links.home_aria_label')" class="
            flex items-center space-x-2
          "
        >
          <span class="flex size-8 items-center justify-center rounded-full">
            <img
              src="/sink.png" :alt="`${title} Logo`" width="32" height="32" class="
                size-full rounded-full
              "
            >
          </span>
          <span class="text-xl font-black">{{ title }}</span>
        </NuxtLink>
        <nav :aria-label="$t('layouts.links.resources_aria_label')">
          <Button as-child variant="ghost" size="icon">
            <a :href="github" target="_blank" rel="noopener noreferrer" :title="$t('layouts.footer.social.github')" :aria-label="$t('layouts.footer.social.github')">
              <GitHubIcon aria-hidden="true" />
            </a>
          </Button>
        </nav>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ArrowRight, Link, QrCode, SlidersHorizontal } from '@lucide/vue'
import { GitHubIcon } from 'vue3-simple-icons'

definePageMeta({ layout: false })

const title = 'Lynk'
const github = 'https://github.com/idmar'
const features = [
  { icon: Link, title: '分享更简洁', description: '将长网址化为简短链接，让消息、邮件和社交分享更清晰。' },
  { icon: QrCode, title: '扫码即达', description: '为短链接生成二维码，轻松连接线上内容与线下场景。' },
  { icon: SlidersHorizontal, title: '链接有序管理', description: '自定义短码、管理目标网址，让每一次分享都有条理。' },
]

useSeoMeta({
  title: '更短的链接，更直接的连接。',
  description: '让分享更简洁。便捷分享、二维码与链接管理。',
})
</script>

<template>
  <div
    lang="zh-CN" class="flex min-h-svh flex-col bg-background text-foreground"
  >
    <Button
      as-child variant="secondary" class="
        fixed top-4 left-4 z-50 -translate-y-24
        focus-within:translate-y-0
      "
    >
      <a href="#main-content">跳至正文</a>
    </Button>
    <header class="border-b">
      <div
        class="
          mx-auto flex max-w-6xl items-center justify-between gap-4 px-6 py-4
        "
      >
        <NuxtLink to="/" aria-label="首页" class="flex items-center space-x-2">
          <span class="flex size-8 items-center justify-center rounded-full">
            <img
              src="/sink.png" :alt="`${title} Logo`" width="32" height="32" class="
                size-full rounded-full
              "
            >
          </span>
          <span class="text-xl font-black">{{ title }}</span>
        </NuxtLink>
        <nav aria-label="主导航" class="flex items-center gap-2">
          <Button as-child variant="ghost" size="sm">
            <NuxtLink to="/dashboard">
              管理登录
            </NuxtLink>
          </Button>
          <SwitchTheme />
        </nav>
      </div>
    </header>
    <main id="main-content" class="flex-1">
      <section
        aria-labelledby="hero-title" class="
          mx-auto max-w-6xl px-6 py-20
          md:py-32
        "
      >
        <div class="max-w-3xl">
          <p
            class="
              mb-6 text-sm font-medium tracking-widest text-muted-foreground
            "
          >
            Lynk, Connect Fast｜快速连结
          </p>
          <h1
            id="hero-title" class="
              text-4xl/tight font-semibold text-balance
              sm:text-5xl
              md:text-6xl
            "
          >
            更短的链接，<br>更直接的连接。
          </h1>
          <p class="mt-6 max-w-xl text-lg/relaxed text-muted-foreground">
            让分享更简洁。把冗长的网址变成轻巧的入口，让值得分享的内容更容易抵达。
          </p>
          <div class="mt-10">
            <Button as-child size="lg">
              <a :href="github" target="_blank" rel="noopener noreferrer">
                <GitHubIcon aria-hidden="true" />访问我的 GitHub<ArrowRight aria-hidden="true" />
              </a>
            </Button>
          </div>
          <p class="mt-4 text-sm text-muted-foreground">
            认识创建者，发现更多项目。
          </p>
        </div>
      </section>
      <section
        aria-labelledby="features-title" class="
          mx-auto max-w-6xl px-6 pb-20
          md:pb-24
        "
      >
        <h2 id="features-title" class="mb-8 text-2xl font-semibold">
          小小链接，轻松分享。
        </h2>
        <div
          class="
            grid gap-4
            md:grid-cols-3
          "
        >
          <Card v-for="feature in features" :key="feature.title">
            <CardHeader>
              <component
                :is="feature.icon" aria-hidden="true" class="
                  mb-4 size-6 text-muted-foreground
                "
              />
              <CardTitle>{{ feature.title }}</CardTitle>
            </CardHeader>
            <CardContent>
              <p class="leading-relaxed text-muted-foreground">
                {{ feature.description }}
              </p>
            </CardContent>
          </Card>
        </div>
      </section>
      <section aria-labelledby="privacy-title" class="border-t bg-muted/40">
        <div
          class="
            mx-auto grid max-w-6xl gap-6 px-6 py-12
            md:grid-cols-2 md:gap-12
          "
        >
          <div>
            <h2 id="privacy-title" class="text-lg font-semibold">
              关于访问与隐私
            </h2>
            <p class="mt-3 text-sm/relaxed text-muted-foreground">
              短链接会将你带到对应的目标网站。服务可能记录访问时间、设备类型和大致地区等信息，用于访问统计；目标网站的隐私政策由其运营者提供。
            </p>
          </div>
          <div>
            <h2 class="text-lg font-semibold">
              联系创建者
            </h2>
            <p class="mt-3 text-sm/relaxed text-muted-foreground">
              如有链接使用问题或项目交流，欢迎通过 GitHub 联系。
            </p>
            <Button as-child variant="link" class="mt-2">
              <a :href="github" target="_blank" rel="noopener noreferrer">github.com/idmar <ArrowRight aria-hidden="true" /></a>
            </Button>
          </div>
        </div>
      </section>
    </main>
    <footer class="border-t">
      <div
        class="
          mx-auto flex max-w-6xl flex-wrap items-center justify-between gap-4
          p-6 text-sm text-muted-foreground
        "
      >
        <p>简洁链接，连接更多。</p>
        <p>
          基于 <a
            href="https://github.com/miantiao-me/Sink" target="_blank" rel="noopener noreferrer" class="
              underline underline-offset-4
            "
          >Sink</a>
          · <a
            href="https://github.com/idmar/Sink" target="_blank" rel="noopener noreferrer" class="
              underline underline-offset-4
            "
          >本站源码</a>
          · <a
            href="https://github.com/miantiao-me/Sink/blob/master/LICENSE" target="_blank" rel="noopener noreferrer" class="
              underline underline-offset-4
            "
          >AGPL-3.0</a>
        </p>
      </div>
    </footer>
  </div>
</template>

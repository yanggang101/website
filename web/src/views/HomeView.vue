<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import { gsap } from 'gsap'
import heroImage from '@/static/imgx-1.png'
import technologyImage from '@/static/imgx-2.png'
import advisoryImage from '@/static/imgx-3.png'
import industryImage from '@/static/imgx-4.png'

const pageRoot = ref(null)
const submitted = ref(false)
let context

const cases = [
  { category: '科技与 AI', title: '把复杂能力，变成清晰的品牌表达', image: technologyImage },
  { category: '专业服务', title: '用克制的设计建立第一份信任', image: advisoryImage },
  { category: '工业制造', title: '让专业实力被全球客户看见', image: industryImage },
]

function scrollToSection(sectionId) {
  document.getElementById(sectionId)?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

function submitInquiry() {
  submitted.value = true
}

onMounted(() => {
  if (!pageRoot.value) return
  context = gsap.context(() => {
    gsap.from('[data-hero-reveal]', {
      autoAlpha: 0,
      y: 28,
      duration: 0.8,
      ease: 'power3.out',
      stagger: 0.12,
    })
  }, pageRoot.value)
})

onUnmounted(() => context?.revert())
</script>

<template>
  <main ref="pageRoot" class="min-h-screen bg-[#06101f] text-[#f4f7fb]">
    <section id="top" class="relative isolate overflow-hidden border-b border-white/10">
      <img :src="heroImage" alt="抽象化的网站设计界面" class="absolute inset-0 -z-20 h-full w-full object-cover object-center opacity-60" />
      <div class="absolute inset-0 -z-10 bg-[#06101f]/70"></div>

      <header class="mx-auto flex max-w-7xl items-center justify-between px-6 py-6 lg:px-8">
        <a href="#top" class="text-lg font-semibold tracking-[0.12em] text-white">智寻科技</a>
        <nav class="hidden items-center gap-7 text-sm text-slate-300 md:flex" aria-label="主导航">
          <a href="#services" class="transition hover:text-white">服务方式</a>
          <a href="#work" class="transition hover:text-white">精选案例</a>
          <a href="#process" class="transition hover:text-white">合作流程</a>
        </nav>
        <button type="button" class="border border-blue-300 bg-blue-500 px-4 py-2 text-sm font-medium text-white transition hover:bg-blue-400" @click="scrollToSection('contact')">获取方案</button>
      </header>

      <div class="mx-auto grid min-h-[680px] max-w-7xl items-center px-6 py-20 lg:grid-cols-12 lg:px-8 lg:py-28">
        <div class="max-w-3xl lg:col-span-8">
          <p data-hero-reveal class="mb-6 text-sm font-medium tracking-[0.18em] text-blue-200">DESIGN · BUILD · DEPLOY</p>
          <h1 data-hero-reveal class="text-5xl font-semibold leading-[1.04] tracking-tight text-white sm:text-6xl lg:text-7xl">
            让企业官网，<span class="text-blue-300">成为增长的起点。</span>
          </h1>
          <p data-hero-reveal class="mt-7 max-w-xl text-base leading-8 text-slate-200 sm:text-lg">从品牌表达、体验设计到正式部署，我们为有长期价值的企业打造真正能转化的数字门面。</p>
          <div data-hero-reveal class="mt-10 flex flex-wrap gap-4">
            <button type="button" class="bg-white px-6 py-3 text-sm font-semibold text-slate-950 transition hover:bg-blue-100" @click="scrollToSection('contact')">开始你的项目</button>
            <a href="#work" class="border border-white/30 px-6 py-3 text-sm font-semibold text-white transition hover:bg-white/10">查看案例</a>
          </div>
        </div>

        <div data-hero-reveal class="mt-16 grid grid-cols-3 gap-6 border-t border-white/15 pt-7 lg:col-span-9 lg:mt-24">
          <div><p class="text-2xl font-semibold text-white">7 天</p><p class="mt-2 text-sm text-slate-300">完成首版提案</p></div>
          <div><p class="text-2xl font-semibold text-white">1 对 1</p><p class="mt-2 text-sm text-slate-300">设计与交付协作</p></div>
          <div><p class="text-2xl font-semibold text-white">全球</p><p class="mt-2 text-sm text-slate-300">部署与访问支持</p></div>
        </div>
      </div>
    </section>

    <section id="services" class="mx-auto max-w-7xl px-6 py-24 lg:px-8 lg:py-32">
      <div class="grid gap-12 lg:grid-cols-12">
        <div class="lg:col-span-5"><p class="text-sm font-medium tracking-[0.18em] text-blue-300">WHAT WE DELIVER</p><h2 class="mt-5 text-4xl font-semibold leading-tight text-white sm:text-5xl">不止一个漂亮页面。</h2></div>
        <div class="grid gap-px border border-white/10 bg-white/10 sm:grid-cols-3 lg:col-span-7">
          <article class="bg-[#0a1728] p-7"><p class="text-sm text-blue-200">01 / 品牌策略</p><h3 class="mt-10 text-xl font-semibold text-white">明确价值与表达</h3><p class="mt-4 text-sm leading-7 text-slate-300">梳理客户、卖点与品牌语调，让官网每一屏都指向商业目标。</p></article>
          <article class="bg-[#0a1728] p-7"><p class="text-sm text-blue-200">02 / 定制设计</p><h3 class="mt-10 text-xl font-semibold text-white">建立可信的体验</h3><p class="mt-4 text-sm leading-7 text-slate-300">为你的行业与受众定制信息架构、视觉系统与关键转化路径。</p></article>
          <article class="bg-[#0a1728] p-7"><p class="text-sm text-blue-200">03 / 上线部署</p><h3 class="mt-10 text-xl font-semibold text-white">交付可持续的站点</h3><p class="mt-4 text-sm leading-7 text-slate-300">完成响应式开发、域名部署、性能优化与上线后的持续支持。</p></article>
        </div>
      </div>
    </section>

    <section id="work" class="border-y border-white/10 bg-[#081527] px-6 py-24 lg:px-8 lg:py-32">
      <div class="mx-auto max-w-7xl">
        <div class="flex flex-wrap items-end justify-between gap-6"><div><p class="text-sm font-medium tracking-[0.18em] text-blue-300">SELECTED WORK</p><h2 class="mt-5 text-4xl font-semibold text-white sm:text-5xl">为不同行业，做同样有力的第一印象。</h2></div><button type="button" class="text-sm font-medium text-blue-200 transition hover:text-white" @click="scrollToSection('contact')">查看适合我的方案</button></div>
        <div class="mt-14 grid gap-8 lg:grid-cols-3">
          <article v-for="item in cases" :key="item.category" class="group">
            <div class="aspect-[3/2] overflow-hidden bg-slate-900"><img :src="item.image" :alt="`${item.category}官网案例`" class="h-full w-full object-cover transition duration-500 group-hover:scale-[1.03]" /></div>
            <p class="mt-5 text-sm text-blue-200">{{ item.category }}</p><h3 class="mt-2 text-xl font-medium text-white">{{ item.title }}</h3>
          </article>
        </div>
      </div>
    </section>

    <section id="process" class="mx-auto max-w-7xl px-6 py-24 lg:px-8 lg:py-32">
      <p class="text-sm font-medium tracking-[0.18em] text-blue-300">HOW WE WORK</p>
      <div class="mt-5 grid gap-12 lg:grid-cols-12"><h2 class="text-4xl font-semibold leading-tight text-white sm:text-5xl lg:col-span-5">从一个想法，到正式上线。</h2>
        <ol class="divide-y divide-white/10 lg:col-span-7">
          <li class="grid grid-cols-[auto_1fr] gap-6 py-6 first:pt-0"><span class="text-sm text-blue-300">01</span><div><h3 class="font-semibold text-white">需求共创</h3><p class="mt-2 text-sm leading-7 text-slate-300">用一场聚焦的访谈，明确目标、受众、内容与交付边界。</p></div></li>
          <li class="grid grid-cols-[auto_1fr] gap-6 py-6"><span class="text-sm text-blue-300">02</span><div><h3 class="font-semibold text-white">设计提案</h3><p class="mt-2 text-sm leading-7 text-slate-300">先确认策略、页面结构与视觉方向，再进入高保真设计。</p></div></li>
          <li class="grid grid-cols-[auto_1fr] gap-6 py-6"><span class="text-sm text-blue-300">03</span><div><h3 class="font-semibold text-white">开发与验收</h3><p class="mt-2 text-sm leading-7 text-slate-300">响应式实现、内容校对、性能与跨设备测试一次完成。</p></div></li>
          <li class="grid grid-cols-[auto_1fr] gap-6 pb-0 pt-6"><span class="text-sm text-blue-300">04</span><div><h3 class="font-semibold text-white">部署与迭代</h3><p class="mt-2 text-sm leading-7 text-slate-300">安全上线、绑定域名，并提供后续内容维护与优化支持。</p></div></li>
        </ol>
      </div>
    </section>

    <section id="contact" class="border-t border-white/10 bg-[#dbeafe] px-6 py-24 text-[#06101f] lg:px-8 lg:py-32">
      <div class="mx-auto grid max-w-7xl gap-12 lg:grid-cols-12"><div class="lg:col-span-5"><p class="text-sm font-medium tracking-[0.18em] text-blue-700">START A PROJECT</p><h2 class="mt-5 text-4xl font-semibold leading-tight sm:text-5xl">准备好，让网站承担更大的价值？</h2><p class="mt-6 max-w-md leading-8 text-slate-700">留下项目基本信息。我们会在一个工作日内联系你，给出初步的合作建议。</p></div>
        <form v-if="!submitted" class="grid gap-4 lg:col-span-6 lg:col-start-7" @submit.prevent="submitInquiry">
          <label class="sr-only" for="company">公司名称</label><input id="company" required type="text" placeholder="公司名称" class="w-full border border-slate-400 bg-transparent px-5 py-4 text-base outline-none transition placeholder:text-slate-500 focus:border-blue-700" />
          <label class="sr-only" for="contact-name">如何称呼你</label><input id="contact-name" required type="text" placeholder="如何称呼你" class="w-full border border-slate-400 bg-transparent px-5 py-4 text-base outline-none transition placeholder:text-slate-500 focus:border-blue-700" />
          <label class="sr-only" for="contact-way">邮箱或微信</label><input id="contact-way" required type="text" placeholder="邮箱或微信" class="w-full border border-slate-400 bg-transparent px-5 py-4 text-base outline-none transition placeholder:text-slate-500 focus:border-blue-700" />
          <label class="sr-only" for="brief">项目概况</label><textarea id="brief" required rows="4" placeholder="简单说说你的业务、目标与期望上线时间" class="w-full resize-none border border-slate-400 bg-transparent px-5 py-4 text-base outline-none transition placeholder:text-slate-500 focus:border-blue-700"></textarea>
          <button type="submit" class="mt-2 w-fit bg-[#06101f] px-7 py-4 text-sm font-semibold text-white transition hover:bg-blue-800">提交项目需求</button>
        </form>
        <div v-else class="border border-slate-400 p-8 lg:col-span-6 lg:col-start-7"><p class="text-sm font-medium text-blue-700">已收到</p><h3 class="mt-4 text-3xl font-semibold">感谢你的项目咨询。</h3><p class="mt-4 leading-8 text-slate-700">这是前端演示状态；接入表单服务后，提交信息将自动发送到你的工作邮箱或 CRM。</p><button type="button" class="mt-7 border border-[#06101f] px-5 py-3 text-sm font-semibold transition hover:bg-[#06101f] hover:text-white" @click="submitted = false">提交另一份需求</button></div>
      </div>
    </section>

    <footer class="bg-[#06101f] px-6 py-8 lg:px-8"><div class="mx-auto flex max-w-7xl flex-wrap items-center justify-between gap-4 text-sm text-slate-400"><p class="font-medium tracking-[0.12em] text-white">智寻科技-CEO__csy</p><p>企业官网定制设计与部署</p></div></footer>
  </main>
</template>

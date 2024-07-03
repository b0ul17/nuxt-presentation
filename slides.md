---
# try also 'default' to start simple
theme: ./theme
# some information about your slides, markdown enabled
title: Why did the developer choose Nuxt?
favicon: '/assets/favicon.ico'
titleTemplate: '%s - Nuxt'
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply any unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Why did the developer choose Nuxt?


<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer text-white" hover="bg-white bg-opacity-10">
    Because they needed something truly Vue-tiful! <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: section
---

# Who Am I?

---
transition: slide-up
level: 2
layout: two-cols
---

## Andreas Panopoulos
<div class="mt-15 text-white">
 <p><span class="mr-2">👉</span> Academy Tech Lead </p>
 <p><span class="mr-2">👉</span>  3,5 years in <span class="text-[#9fef00]">Hack The Box</span></p>


 <h3  class="mt-5"> "What I Love to Do" </h3>
 <div v-click>
 <p><span class="mr-2">👉</span> Cycling </p>
  <p><span class="mr-2">👉</span> Photography</p>
 <p><span class="mr-2">👉</span> Music</p>
 <p><span class="mr-2">👉</span> Punjokes</p>
 </div>
</div>




 
<div v-click >

> 'Εξυπνος έλληνας τραγουδιστής <br> Τσακαλίκης 

</div>

<div v-click class="mt-2">

> Why did the scarecrow got an award. <br>
Because it was outstanding in it's field!

</div> 


::right::

<div v-motion
  :initial="{ x: 180 }"
  :enter="{ x: 0, y: 0 }"
  :click-1="{ x: 0, y: 30 }"
  :click-2-4="{ x: 40 }"
  :leave="{ y: 0, x: 80 }"
>
  <img
    src="https://media.giphy.com/media/LYKCFkG2vmATCoqJUJ/giphy.gif?cid=790b7611zytwvb0zbp7n1v11stf8jwsvu1sbbyznxs81urat&ep=v1_gifs_search&rid=giphy.gif&ct=g"
    alt="who is he"
  />

</div>

 <style>
  h2 {
    color: white;
  }
</style>

---
transition: slide-up
layout: section
---

# What is nuxt?

---
transition: slide-down
layout: center
---

Nuxt is a free and open-source framework with an intuitive and extendable way to create type-safe, performant and production-grade full-stack web applications and websites with Vue.js
 [learn more](https://nuxt.com/)


<style>
  a{
    color: #9fef00;
  }
</style>


---
transition: slide-up
layout: default-2
---

# Project File Structure


Nuxt.js offers a clear and well-organized project structure that significantly simplifies managing your Vue.js codebase. This is especially advantageous for larger projects where maintaining an organized codebase can be challenging. Nuxt's structure ensures that your code stays clean and easy to navigate, regardless of the project's complexity.

<img
  v-click
  class="mt-15"
  src="/assets/app.png"
  alt="nuxt app"
/>

---
transition: slide-right
---

# File Based routing

Nuxt includes a file-based routing system that removes the need for manual route configuration in most cases. Rather than manually setting up routes, you simply create specific Vue files for each route within the pages directory. This intuitive and convenient method allows you to easily map your application's structure in a way that directly aligns with your project's file architecture.

<img
  v-click
  class="mt-15"
  src="/assets/hello-world.png"
  alt="hello world"
/>

<img
  v-click
  class="mt-15"
  src="/assets/id-vue.png"
  alt="dynamic routing"
/>



<!--
 <NuxtPage> is a wrapper around <RouterView> component from Vue Router.

 Nuxt automatically resolves the name and route by scanning and rendering all Vue component files found in the /pages directory.
-->

---
transition: slide-left
---

# Auto-imports

Nuxt.js simplifies the development process with auto-importing feature. 
This feature automatically imports components, composables, and utilities, helper functions and Vue APIs, reducing the need for repetitive import statements and allowing developers to focus more on building functionality.

<div class="mt-20">


````md magic-move {lines: true}
```vue {*|4-5}
// example 1 
<script setup lang="ts">
/* ref() and computed() are auto-imported */
const count = ref(1)
const double = computed(() => count.value * 2)
</script>
```

```vue {*|4}
// example 2
<script setup lang="ts">
/* useFetch composable is auto-imported */
const { data, refresh, pending } = await useFetch('/api/hello')
</script>
```
````
</div>
<div v-click class="mt-5">
```ts
// nuxt.config.ts
export default defineNuxtConfig({
  imports: {
    autoImport: false
  }
})
```
</div>

---
transition: slide-down
layout: default-5
---
# Server-Side Rendering

Benefits of server-side rendering:

-   Faster initial page load time: Nuxt sends a fully rendered HTML page to the browser, which can be displayed immediately. This can provide a faster perceived page load time and a better user experience (UX), especially on slower networks or devices.
-   Improved SEO: search engines can better index SSR pages because the HTML content is available immediately, rather than requiring JavaScript to render the content on the client-side.
-   Better performance on low-powered devices: it reduces the amount of JavaScript that needs to be downloaded and executed on the client-side, which can be beneficial for low-powered devices that may struggle with processing heavy JavaScript applications.
-   Better accessibility: the content is immediately available on the initial page load, improving accessibility for users who rely on screen readers or other assistive technologies.
-   Easier caching: pages can be cached on the server-side, which can further improve performance by reducing the amount of time it takes to generate and send the content to the client.

Overall, server-side rendering can provide a faster and more efficient user experience, as well as improve search engine optimization and accessibility.


<style>
  li{
    color: white;
    font-size:12px;
    font-weight: 300;
  }
</style>


---
transition: slide-up
layout: default-6
---

Downsides of server-side rendering:

-   Development constraints: Server and browser environments don't provide the same APIs, and it can be tricky to write code that can run on both sides seamlessly. Fortunately, Nuxt provides guidelines and specific variables to help you determine where a piece of code is executed.
-   Cost: A server needs to be running in order to render pages on the fly. This adds a monthly cost like any traditional server. However, the server calls are highly reduced thanks to universal rendering with the browser taking over on client-side navigation. A cost reduction is possible by leveraging [edge-side-rendering](https://nuxt.com/docs/guide/concepts/rendering#edge-side-rendering).


The current platforms where you can leverage ESR are:

-   [Cloudflare Pages](https://pages.cloudflare.com/) with zero configuration using the git integration and the `nuxt build` command
-   [Vercel Edge Functions](https://vercel.com/features/edge-functions) using the `nuxt build` command and `NITRO_PRESET=vercel-edge` environment variable
-   [Netlify Edge Functions](https://www.netlify.com/products/#netlify-edge-functions) using the `nuxt build` command and `NITRO_PRESET=netlify-edge` environment variable




<style>
  li{
    color: white;
    font-size:12px;
    font-weight: 300;
    margin-bottom: 20px;
  }
</style>


---
transition: slide-down
layout: default-4
---
# Client-Side Rendering

Benefits of client-side rendering:

-   Development speed: When working entirely on the client-side, we don't have to worry about the server compatibility of the code, for example, by using browser-only APIs like the `window` object.
-   Cheaper: Running a server adds a cost of infrastructure as you would need to run on a platform that supports JavaScript. We can host Client-only applications on any static server with HTML, CSS, and JavaScript files. 



<style>
  li{
    color: white;
    font-size:12px;
    font-weight: 300;
    margin-bottom: 20px;
  }
</style>


---
transition: slide-up
layout: default-3
---

Downsides of client-side rendering:

-   Performance: The user has to wait for the browser to download, parse and run JavaScript files. Depending on the network for the download part and the user's device for the parsing and execution, this can take some time and impact the user's experience.
-   Search Engine Optimization: Indexing and updating the content delivered via client-side rendering takes more time than with a server-rendered HTML document. This is related to the performance drawback we discussed, as search engine crawlers won't wait for the interface to be fully rendered on their first try to index the page. Your content will take more time to show and update in search results pages with pure client-side rendering.


You can enable client-side only rendering with Nuxt in your nuxt.config.ts

<div v-click>
```ts
export default defineNuxtConfig({
  ssr: false
})

```
</div>


<style>
  li{
    color: white;
    font-size:12px;
    font-weight: 300;
    margin-bottom: 20px;
  }
</style>

---
transition: slide-left
layout: default-4
---

# Modular Architecture

Nuxt.js is designed with a modular architecture that promotes reusability, maintainability, and flexibility. This modular approach allows developers to build complex applications with a clear separation of concerns and the ability to easily extend functionality.


<img
  v-click
  class="mt-5"
  src="/assets/modules.png"
  alt="nuxt app"
/>

---
transition: slide-left
layout: default-7
---

# Extensibility
  Nuxt.js is modular, allowing developers to easily extend and enhance the functionality, integrating modules for various purposes, such as 
  Nuxt Laravel Sanctum authentication (nuxt-auth-sanctum), PWA support (@nuxt/pwa), Pinia Store (@pinia/nuxt).

````md magic-move {lines: true}
```ts {*|2}
// step 1 
npm i @pinia/nuxt
```

```ts {*|4|6}
// step 2 nuxt.config.ts
export default defineNuxtConfig({
    modules: [
      '@pinia/nuxt',
      // Load a local module
      './modules/example',
    ],
})
```
````
---
transition: slide-up
layout: default-2 
---


# Code Splitting
Built-in code splitting ensures that only the necessary code is loaded for each page, improving performance and and initial load time of the application.

<img
  v-click
  class="mt-5"
  src="/assets/chunks.png"
  alt="code splitting chunks"
/>

---
transition: slide-left
level: 2
---

# Build Fullstack Apps

Nuxt utilizes Nitro an open source framework to build web servers using unjs/h3 and lots of built-in features.

<img
  v-click
  class="mt-5"
  src="/assets/nitro.png"
  alt="nitro server"
/>



---
layout: section-3
---

# Questions
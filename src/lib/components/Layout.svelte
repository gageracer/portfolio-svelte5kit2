<script lang="ts">
 	import { resolve } from "$app/paths";

let { siteTitle = "John's Portfolio", children } = $props();
</script>

<svelte:head>
    <title>{siteTitle}</title>
</svelte:head>
<div class="container mx-auto max-w-2xl px-4 py-8">
    <section class="prose prose-invert mb-8">
      <p>
        Hi, my name is John. I'm a computer engineer and I build things for the web.
        You can contact me on <a href={resolve("https://www.linkedin.com/in/can-aygin")} target="_blank">LinkedIn</a>
        and my resume is on the navigation bar.
      </p>
      <p>
        Here is some of my work so far. There are more if you want to check on my
        <a href={resolve("https://github.com/gageracer")} target="_blank">GitHub</a> like games,
        small prototypes and such.
      </p>
    </section>

  {@render children()}
</div>

<script>
	import { page } from '$app/state';

	const home = $derived(page.url.pathname === '/');
</script>

<!-- Social Links -->
<nav class={['mt-8 w-full md:left-10 md:w-auto', {'relative bottom-0 z-10 md:fixed': !home} ]}>
    <ul
		class={['flex flex-row items-center justify-center space-x-5',!home && 'md:flex-col md:space-y-4 md:space-x-0']}
	>
       <li class="w-6">
         <a href="https://github.com/gageracer" target="_blank" title="GitHub">
           <img src="/images/svgs/github.svg" alt="github" />
         </a>
       </li>
       <li class="w-6">
         <a href="https://www.codewars.com/users/gageracer/stats" title="CodeWars" target="_blank">
           <img src="/images/svgs/codewars.svg" alt="codewars" />
         </a>
       </li>
       <li class="w-6">
         <a href="https://www.linkedin.com/in/can-aygin" title="LinkedIn" target="_blank">
           <img alt="linkedin" src="/images/svgs/linkedin.svg" />
         </a>
       </li>
       <li class="w-6">
         <a href="/resume/John's Resume.pdf" title="Resume" target="blank">
           <img alt="resume" src="/images/svgs/resume.svg" />
         </a>
       </li>
     </ul>
     <!-- Vertical line after social icons - only shows on md and up -->
     {#if !home}
        <div class="hidden md:block mt-4 h-24 w-px mx-auto bg-text/30"></div>
	{/if}
   </nav>

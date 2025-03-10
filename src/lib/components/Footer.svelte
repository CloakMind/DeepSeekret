<script lang="ts">
  import { Separator } from "$lib/components/ui/separator";
</script>

<footer id="footer" class="container py-24 pb-16 sm:py-32 sm:pb-24">
  <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
    <div class="grid grid-cols-2 md:grid-cols-4 xl:grid-cols-6 gap-x-12 gap-y-8">
      <div class="col-span-full xl:col-span-2">
        <a href="https://github.com/cloakmind" class="flex font-bold items-center">
          <img
            src="/favicon.png"
            alt="Beach"
            class="w-9 h-9 mr-2"
          />
          <h3 class="text-2xl">DeepSeekret</h3>
        </a>
      </div>

      <div class="flex flex-col gap-2">
        <h3 class="font-bold text-lg">Contact</h3>
        <div><a href="https://discord.gg/N3m6Xn6wmQ" class="opacity-60 hover:opacity-100">Discord</a></div>
        <div><a href="https://github.com/cloakmind" class="opacity-60 hover:opacity-100">GitHub</a></div>
        <div><a href="https://twitter.com" class="opacity-60 hover:opacity-100">Twitter</a></div>
      </div>

      <div class="flex flex-col gap-2">
        <h3 class="font-bold text-lg">Platforms</h3>
        <div><a href="/" class="opacity-60 hover:opacity-100">Web - try now!</a></div>
        <div><span class="opacity-60 cursor-default">iOS - soon!</span></div>
        <div><span class="opacity-60 cursor-default">Android - soon!</span></div>
      </div>

      <div class="flex flex-col gap-2">
        <h3 class="font-bold text-lg">Help</h3>
        <div><a href="mailto:cloakmind@gmail.com" class="opacity-60 hover:opacity-100">Contact Us</a></div>
        <div><a href="#faq" class="opacity-60 hover:opacity-100">FAQ</a></div>
        <div><a href="https://github.com/CloakMind/DeepSeekret/issues" class="opacity-60 hover:opacity-100">Feedback</a></div>
      </div>

      <div class="flex flex-col gap-2">
        <h3 class="font-bold text-lg">Socials</h3>
        <div><a href="https://instagram.com" class="opacity-60 hover:opacity-100">Instagram</a></div>
        <div><a href="https://www.reddit.com/r/CloakMind" class="opacity-60 hover:opacity-100">Reddit</a></div>
        <div><a href="https://www.youtube.com" class="opacity-60 hover:opacity-100">Youtube</a></div>
      </div>
    </div>

    <Separator class="my-6" />
    
    <section>
      <h3>
        &copy; 2025, A
        <a
          target="_blank"
          href="https://github.com/CloakMind"
          class="text-primary transition-all border-primary hover:border-b-2"
          rel="noreferrer"
        >
          CloakMind
        </a>
        initiative
      </h3>
    </section>
  </div>
</footer>

<script lang="ts">
  import {
    Crown,
    Vegan,
    Ghost,
    Puzzle,
    Squirrel,
    Cookie,
    Drama
  } from "lucide-svelte";

  interface BannerProps {
    icon: 'crown' | 'vegan' | 'ghost' | 'puzzle' | 'squirrel' | 'cookie' | 'drama';
    name: string;
  }

  const item: BannerProps[] = [
    { icon: "crown", name: "Ease of Use" },
    { icon: "vegan", name: "Security" },
    { icon: "crown", name: "Free" },
    { icon: "vegan", name: "Open Source" },
    { icon: "ghost", name: "DeepSeekret" },
    { icon: "puzzle", name: "Privacy" },
    { icon: "squirrel", name: "CloakMind" },
    { icon: "cookie", name: "Unlimited Usage" },
    { icon: "drama", name: "Local" },
  ];

  const iconMap = {
    crown: Crown,
    vegan: Vegan,
    ghost: Ghost,
    puzzle: Puzzle,
    squirrel: Squirrel,
    cookie: Cookie,
    drama: Drama,
  };
</script>

<section id="banner" class="mx-auto pt-4 pb-4 sm:pb-8 sm:pt-8">
  <div class="mx-auto overflow-hidden">
    <div class="flex animate-marquee gap-12 w-max">
      {#each item as { icon, name }}
        <div class="flex items-center text-xl md:text-2xl font-medium whitespace-nowrap">
          <svelte:component this={iconMap[icon]} class="mr-2" strokeWidth={3} />
          {name}
        </div>
      {/each}
      {#each item as { icon, name }}
        <div class="flex items-center text-xl md:text-2xl font-medium whitespace-nowrap">
          <svelte:component this={iconMap[icon]} class="mr-2" strokeWidth={3} />
          {name}
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-51%); }
  }

  .animate-marquee {
    animation: marquee 25s linear infinite;
  }

  .animate-marquee:hover {
    animation-play-state: paused;
  }
</style>

<script lang="ts">
  import { Card, CardContent, CardHeader, CardTitle } from "$lib/components/ui/card";
  import {
    Sparkle,
    GitPullRequestArrow,
    ChartLine,
    VideoOff,
  } from "lucide-svelte";

  interface BenefitsProps {
    icon: 'videoOff' | 'gitPullRequestArrow' | 'chartLine' | 'sparkle';
    title: string;
    description: string;
  }

  const benefitList: BenefitsProps[] = [
    {
      icon: "videoOff",
      title: "Secure",
      description:
        "Your data should stay with you. DeepSeekret runs in your browser, so nothing is sent to servers.",
    },
    {
      icon: "gitPullRequestArrow",
      title: "Open Source",
      description:
        "Trust what you use. DeepSeekret is fully open-source, meaning you can review and contribute to it.",
    },
    {
      icon: "chartLine",
      title: "100% Free",
      description:
        "DeepSeekret is completely free to use, with no subscriptions, no hidden fees, and no restrictions.",
    },
    {
      icon: "sparkle",
      title: "Ease of Use",
      description:
        "No additional installs or setup required, just open your browser and start generating.",
    },
    {
      icon: "sparkle",
      title: "Unlimited Usage",
      description:
        "use as much as you need, use model to its full capability.",
    },
  ];

  const iconMap = {
    videoOff: VideoOff,
    gitPullRequestArrow: GitPullRequestArrow,
    chartLine: ChartLine,
    sparkle: Sparkle,
  };
</script>

<section id="benefits" class="container py-24 sm:py-32">
  <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
    <div>
      <h2 class="text-lg text-primary mb-2 tracking-wider">Why DeepSeekret</h2>
      <h2 class="text-3xl md:text-4xl font-bold mb-4">
        Run DeepSeek Locally & Privately
      </h2>
      <p class="text-xl text-muted-foreground mb-8">
        Shorter, more sensible
      </p>
    </div>

    <div class="grid lg:grid-cols-2 gap-4 w-full">
      {#each benefitList as { icon, title, description }, index}
        <Card class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number">
          <CardHeader>
            <div class="flex justify-between">
              <svelte:component 
                this={iconMap[icon]} 
                class="size-8 mb-6 text-primary"
              />
              <span class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30">
                0{index + 1}
              </span>
            </div>
            <CardTitle>{title}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {description}
          </CardContent>
        </Card>
      {/each}
    </div>
  </div>
</section>

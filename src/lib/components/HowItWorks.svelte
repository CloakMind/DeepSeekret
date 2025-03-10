<script lang="ts">
  import { Card, CardContent, CardHeader, CardTitle } from "$lib/components/ui/card";
  import { Badge } from "$lib/components/ui/badge";

  interface HowItWorksProps {
    badgeTitle: string;
    title: string;
    description: string;
    image: string;
  }

  const HowItWorksList: HowItWorksProps[] = [
    {
      badgeTitle: "Launch",
      title: "Open DeepSeekret",
      description:
        "No installation needed. Everything runs directly in your browser.",
      image: "chat.png",
    },
    {
      badgeTitle: "Download once",
      title: "One time download to your device",
      description:
        "DeepSeekret loads the selected model directly into your browser.",
      image: "blob.gif",
    },
    {
      badgeTitle: "Chat securely",
      title: "Run AI locally and start chatting securely",
      description:
        "Get instant results without sending your prompts or responses to any server.",
      image: "privacy.png",
    },
  ];
</script>

<section id="how-it-works" class="container py-24 sm:py-32">
  <div class="text-center mb-8">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      How It Works
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold">
      In-browser execution
    </h2>
  </div>

  <div class="lg:w-[80%] mx-auto relative">
    {#each HowItWorksList as { badgeTitle, title, description, image }, index}
      <div class="flex mb-8 items-center" class:flex-row-reverse={index % 2 !== 0} class:text-right={index % 2 !== 0}>
        <Card class="h-full bg-transparent border-0 shadow-none w-[80%]">
          <CardHeader>
            <div class="pb-4">
              <Badge>{badgeTitle}</Badge>
            </div>

            <CardTitle>
              {title}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {description}
          </CardContent>
        </Card>

        <img
          src={image}
          alt="Image describing {title}"
          class="w-[150px] md:w-[250px] lg:w-[300px] mx-auto"
        />
        
        <div
          class="-z-10 absolute right-0 w-44 h-72 lg:w-64 lg:h-80 rounded-full bg-primary/15 dark:bg-primary/10 blur-3xl"
          class:left-0={index % 2 !== 0}
        ></div>
      </div>
    {/each}
  </div>
</section>

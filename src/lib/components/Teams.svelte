<script lang="ts">
  import {
    Card,
    CardContent,
    CardHeader,
    CardTitle,
    CardFooter,
  } from "$lib/components/ui/card";

  import { Globe } from "lucide-svelte";
  import LinkedInIcon from "$lib/icons/LinkedInIcon.svelte";
  import GithubIcon from "$lib/icons/GithubIcon.svelte";
  import XIcon from "$lib/icons/XIcon.svelte";

  interface TeamProps {
    imageUrl: string;
    firstName: string;
    lastName: string;
    positions: string[];
    socialNetworks: SocialNetworkProps[];
  }

  interface SocialNetworkProps {
    name: 'Website' | 'LinkedIn' | 'Github' | 'X';
    url: string;
  }

  const teamList: TeamProps[] = [
  {
    imageUrl:
      "https://media.licdn.com/dms/image/v2/C4D03AQFLYKr9ofNeVw/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1600798019113?e=1746057600&v=beta&t=wYBEuRXr9ziHeMPV5Kg_CIUsyNr4sUPANRPMxz40FzM",
    firstName: "Shivang",
    lastName: "Agrawal",
    positions: ["Co-Founder"],
    socialNetworks: [
      {
        name: "LinkedIn",
        url: "https://www.linkedin.com/in/shivangagr",
      },
      {
        name: "Github",
        url: "https://github.com/shivangagr",
      },
    ],
  },
  {
    imageUrl:
      "https://media.licdn.com/dms/image/v2/D4D03AQGHdAiqvXA6Iw/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1674191569594?e=1746057600&v=beta&t=hQF5MCRCAniMqdj9FND1AaY_fhOO07Pn6DRNbgWU0gE",
    firstName: "Mitul",
    lastName: "Agrawal",
    positions: ["Co-Founder"],
    socialNetworks: [
      {
        name: "Github",
        url: "https://github.com/mitulagr2",
      },
      {
        name: "Website",
        url: "https://mitulagr2.vercel.app",
      },
    ],
  },
  ];

  const socialIconMap = {
    Website: Globe,
    LinkedIn: LinkedInIcon,
    Github: GithubIcon,
    X: XIcon,
  };
</script>

<section id="team" class="container max-w-7xl mx-auto px-4 py-16 sm:py-24 lg:py-32">
  <div class="text-center mb-12">
    <h2 class="text-lg text-primary text-center mb-3 tracking-wider">Team</h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold">
      The Minds Behind DeepSeekret
    </h2>
  </div>

  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8 justify-center items-start">
    <div class="hidden lg:block"></div>
    {#each teamList as { imageUrl, firstName, lastName, positions, socialNetworks }}
      <Card class="bg-muted/60 dark:bg-card flex flex-col h-full overflow-hidden group/hoverimg">
        <CardHeader class="p-0 gap-0">
          <div class="h-full overflow-hidden">
            <img
              src={imageUrl}
              alt={`${firstName} ${lastName}`}
              class="w-full aspect-square object-cover saturate-0 transition-all duration-300 ease-in-out group-hover/hoverimg:saturate-100 group-hover/hoverimg:scale-105"
            />
          </div>
          <CardTitle class="p-4 sm:p-6">
            {firstName}
            <span class="text-primary">{lastName}</span>
          </CardTitle>
        </CardHeader>

        <div class="px-4 sm:px-6 flex-grow">
          {#each positions as position, index}
            <CardContent class="p-0 pb-2 text-muted-foreground">
              {position}{#if index < positions.length - 1},{/if}
            </CardContent>
          {/each}
        </div>

        <CardFooter class="space-x-4 px-4 sm:px-6 py-4">
          {#each socialNetworks as { name, url }}
            <a
              href={url}
              target="_blank"
              class="hover:opacity-80 transition-opacity"
              aria-label="Visit our {name} page"
            >
              <svelte:component this={socialIconMap[name]} class="w-[20px] h-[20px]" />
            </a>
          {/each}
        </CardFooter>
      </Card>
    {/each}
  </div>
</section>

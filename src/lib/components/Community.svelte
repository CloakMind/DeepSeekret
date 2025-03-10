<script lang="ts">
  import {
    Card,
    CardHeader,
    CardTitle,
    CardFooter,
    CardContent,
  } from "$lib/components/ui/card";
  import { Button } from "$lib/components/ui/button";
  import DiscordIcon from "$lib/icons/DiscordIcon.svelte";
  import { ArrowRight } from "lucide-svelte";
</script>

<section id="community" class="py-12">
  <hr />
  <div class="container py-20 sm:py-20">
    <div class="lg:w-[60%] mx-auto">
      <Card class="bg-background shadow-none text-center flex flex-col items-center justify-center border-0">
        <CardHeader>
          <CardTitle class="text-4xl md:text-5xl font-bold">
            <DiscordIcon class="w-20 h-20 m-auto mb-4" />
            Ready to join this
            <span class="text-transparent bg-gradient-to-r from-primary to-[#C59A34] bg-clip-text">
              Community?
            </span>
          </CardTitle>
        </CardHeader>
        <CardContent class="lg:w-[80%] text-xl text-muted-foreground">
          Join us in building a secure and transparent future of AI where people have ownership and privacy over their data!
        </CardContent>

        <CardFooter class="flex gap-4">
          <Button class="font-bold group/arrow">
            <a href="https://discord.gg/vJZed2vqME" class="flex">
                Join Discord
                <ArrowRight
                    class="size-5 ml-2 group-hover/arrow:translate-x-1 transition-transform"
                />
            </a>
          </Button>
          <Button variant="ghost" class="font-bold group/arrow">
            <a href="https://github.com/CloakMind/DeepSeekret" target="_blank" rel="noreferrer" class="flex">
                Star us on GitHub
            </a>
          </Button>
        </CardFooter>
      </Card>
    </div>
  </div>
  <hr />
</section>

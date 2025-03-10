<script lang="ts">
    import { Badge } from "$lib/components/ui/badge";
    import { Button } from "$lib/components/ui/button";
    import { ArrowRight } from "lucide-svelte";
    import { mode } from "mode-watcher";
    import { onMount } from 'svelte';

    let imageSrc = '/hero-image-light.png';
    
    onMount(() => {
        mode.subscribe(currentMode => {
            imageSrc = currentMode === 'dark' ? '/hero-image-dark.png' : '/hero-image-light.png';
        });
    });
</script>

<section class="container">
    <div
        class="grid place-items-center lg:max-w-screen-xl gap-8 mx-auto pb-20 pt-16 md:pb-32 md:pt-24"
    >
        <div class="text-center space-y-8">
            <Badge variant="outline" class="text-sm py-2">
                <span class="mr-2 text-primary">
                    <Badge class="bg-[#FCD400]">New</Badge>
                </span>
                <span>Chat model out now!</span>
            </Badge>

            <div
                class="max-w-screen-md mx-auto text-center text-5xl md:text-6xl font-bold"
            >
                <h1>
                    Keep your chats a
                    <span
                        class="text-transparent bg-gradient-to-r from-primary to-[#C59A34] bg-clip-text"
                    >
                        DeepSeekret
                    </span>
                </h1>
            </div>

            <p class="max-w-screen-sm mx-auto text-xl text-muted-foreground">
                Run DeepSeek locally in your browser. Secure, open-source, and free.
                No cloud processing, no data leaks, your data never leaves your device.
            </p>

            <div class="space-y-4 md:space-y-0 md:space-x-4">
                <Button class="w-5/6 md:w-1/4 font-bold group/arrow">
                    <a href="/" class="flex">
                        Try Now for Free
                        <ArrowRight
                            class="size-5 ml-2 group-hover/arrow:translate-x-1 transition-transform"
                        />
                    </a>
                </Button>

                <Button variant="ghost" class="w-5/6 md:w-1/4 font-bold">
                    <a
                        href="https://github.com/CloakMind/DeepSeekret"
                        target="_blank"
                        rel="noreferrer"
                    >
                        Star us on GitHub
                    </a>
                </Button>
            </div>
        </div>

        <div class="relative group mt-14">
            <div
                class="absolute -top-6 right-12 w-[90%] h-12 lg:h-[80%] bg-primary/50 blur-3xl rounded-full img-shadow-animation"
            ></div>

            <img
                class="w-full md:w-[1200px] mx-auto rounded-lg relative rouded-lg leading-none flex items-center"
                src={imageSrc}
                alt="dashboard using shadcn-svelte"
            />

            <div
                class="absolute bottom-0 left-0 w-full h-20 md:h-28 bg-gradient-to-b from-background/0 via-background/50 to-background rounded-lg"
            ></div>
        </div>
    </div>
</section>

<style>
    .img-shadow-animation {
        animation-name: img-shadow-animation;
        animation-iteration-count: infinite;
        animation-duration: 2s;
        animation-timing-function: linear;
        animation-direction: alternate;
    }
    
    @keyframes img-shadow-animation {
        from {
            opacity: 0.5;
            transform: translateY(30px);
        }

        to {
            opacity: 1;
            transform: translateY(0px);
        }
    }
</style>

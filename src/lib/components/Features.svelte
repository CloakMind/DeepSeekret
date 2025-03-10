<script lang="ts">
  import {
    Card,
    CardDescription,
    CardHeader,
    CardTitle,
  } from "$lib/components/ui/card";
  import { Badge } from "$lib/components/ui/badge";

  const ProFeature = {
    YES: 1,
    NO: 0,
  } as const;

  type ProFeatureType = typeof ProFeature[keyof typeof ProFeature];

  interface FeatureProps {
    title: string;
    pro: ProFeatureType;
    description: string;
  }

  const featureList: FeatureProps[] = [
    {
      title: "DeepSeek Chat Model",
      description:
        "Private, local AI chat for instant assistance in writing, brainstorming, and coding.",
      pro: 0,
    },
    {
      title: "Model Configuration",
      description: "Choose from different DeepSeek model variations to match your needs.",
      pro: 0,
    },
    {
      title: "Other Models",
      description: "Choose from different DeepSeek model variations to match your needs.",
      pro: 1,
    },
    {
      title: "RAG (Retrieval Augmented Generation)",
      description: "Upload documents and get AI-powered answers based on your own data.",
      pro: 1,
    },
    {
      title: "Image Inference",
      description:
        "Extract text, recognize objects, and analyze images-all locally.",
      pro: 1,
    },
  ];
</script>

<section id="features" class="container py-24 sm:py-32">
  <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
    Features
  </h2>

  <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
    Your Local AI Toolkit
  </h2>
  <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
    Discover the range of AI features, powered by local DeepSeek processing, all within your browser.
  </h3>

  <div class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[60%] mx-auto">
    {#each featureList as { title, description, pro }}
      <Card class="bg-muted/60 dark:bg-card h-full pb-6 relative">
        <CardHeader>
          <CardTitle>{title}</CardTitle>
          <CardDescription>{description}</CardDescription>
        </CardHeader>
        {#if pro === ProFeature.YES}
          <Badge variant="secondary" class="absolute -top-2 -right-3 bg-background border-primary text-primary">
            SOON
          </Badge>
        {/if}
      </Card>
    {/each}
  </div>
</section>

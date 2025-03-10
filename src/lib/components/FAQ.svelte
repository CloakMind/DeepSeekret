<script lang="ts">
  import {
    Accordion,
    AccordionContent,
    AccordionItem,
    AccordionTrigger,
  } from "$lib/components/ui/accordion";

  interface FAQProps {
    question: string;
    answer: string;
  }

  const FAQList: FAQProps[] = [
    {
      question: "How much does this cost?",
      answer: "Lorem ipsum",
    },
    {
      question: "Which DeepSeek model is being run in the browser?",
      answer: "DeepSeekret uses a distilled version of DeepSeek",
    },
    {
      question: "Do I need a powerful computer to run DeepSeekret?",
      answer:
        "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sint labore quidem quam consectetur sapiente, iste rerum reiciendis animi nihil nostrum sit quo, modi quod.",
    },
    {
      question:
        "Why should I trust DeepSeekret with my data?",
      answer:
        "network tab cpu usage.",
    },
    {
      question:
        "Performance?",
      answer:
        "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Labore qui nostrum reiciendis veritatis.",
    },
    {
      question:
        "Features?",
      answer:
        "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Labore qui nostrum reiciendis veritatis.",
    },
    {
      question:
        "What browsers are supported?",
      answer:
        "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Labore qui nostrum reiciendis veritatis.",
    },
    {
      question: "Does DeepSeekret work offline?",
      answer: "Lorem ipsum dolor sit amet consectetur, adipisicing elit.",
    },
    {
      question:
        "How can I contribute to DeepSeekret?",
      answer:
        "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Labore qui nostrum reiciendis veritatis.",
    },
  ];
</script>

<section id="faq" class="container md:w-[700px] py-24 sm:py-32">
  <div class="text-center mb-8">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">FAQS</h2>
    <h2 class="text-3xl md:text-4xl text-center font-bold">
      Common Questions
    </h2>
  </div>

  <Accordion class="w-full">
    {#each FAQList as { question, answer }, i}
      <AccordionItem value={`item-${i + 1}`}>
        <AccordionTrigger class="text-left">
          {question}
        </AccordionTrigger>
        <AccordionContent>
          {answer}
        </AccordionContent>
      </AccordionItem>
    {/each}
  </Accordion>

  <h3 class="font-medium mt-8 text-muted-foreground">
    Where can I get support or ask further questions?
    <a href="https://discord.gg/bFFmyKZR8P" target="_blank" rel="noreferrer" class="text-foreground underline hover:text-primary">
      Join our community
    </a>
  </h3>
</section>

<!--
    @component
    A call-to-action component that attracts attention and encourages user engagement.

    Usage:
    ```html
    <CallToAction
      title="Get started today"
      subtitle="Join now"
      description="Ready to experience the difference? Join our community of satisfied customers and see how our solution can transform your workflow."
      image="https://www.unc.mn/image-placeholder.svg"
      callsToAction={[
        {
          href: "/get-started",
          label: "Get Started",
          variant: "primary"
        },
        {
          href: "/contact",
          label: "Talk to Sales",
          variant: "secondary"
        }
      ]}
    />
    ```

    Props:
    - `title`: The main heading text (string)
    - `subtitle`: Secondary heading text (string)
    - `description`: Detailed information about the offer (string)
    - `callsToAction`: Array of CTA objects with href, label, and optional variant properties (CTA[])
    - `imageSrc`: portrait of the company's customer smiling at the camera.
-->

<script lang="ts">
	// Types
	import type { ComponentProps } from "svelte";

	// Components
	import Button from "../ui/Button.svelte";
	import AnimateText from "../animation/AnimateText.svelte";
	import { cta } from "$lib/navigation";
	
	// Icons
	import IconArrowRight from "~icons/lucide/arrow-right";
	import IconBookOpen from "~icons/lucide/book-open";

	// Types
	type CTA = {
		href: string;
		label: string;
		variant?: ComponentProps<typeof Button>["variant"];
	};

	// Props
	const {
		title = "Get started today",
		subtitle = "Join now",
		description = "Ready to experience the difference? Join our community of satisfied customers and see how our solution can transform your workflow. ",
		imageSrc = "https://www.unc.mn/image-placeholder.svg",
		callsToAction = [cta],
		...rest
	}: {
		title?: string;
		subtitle?: string;
		description?: string;
		imageSrc?: string;
		callsToAction?: CTA[];
		[key: string]: any;
	} = $props();
</script>

<div class="" {...rest}>
	<section class="section-px section-py container mx-auto">
		<div
			class="bg-card border-border grid content-start items-center justify-between gap-(--gap) rounded-(--radius) border p-(--gap) text-balance transition-all duration-500 hover:scale-[1.01] [--gap:--spacing(8)] [--inner-radius:calc(var(--radius)-var(--gap))] [--radius:var(--radius-xl)] lg:grid-cols-[2fr_1fr]"
		>
			<div class="items-between grid h-full content-between gap-16">
				<h2 class="text-title1 mb-3 flex flex-col">
					<span class="transition-colors duration-300"><AnimateText text={title} /></span>
					<span class="text-emphasis-low transition-colors duration-300"><AnimateText text={subtitle} /></span>
				</h2>
				<div class="flex flex-col items-start justify-start gap-7">
					<p class="text-headline text-emphasis-low leading-relaxed">
						{description}
					</p>
					<div class="flex w-full flex-col gap-3 md:flex-row md:flex-wrap">
						{#each callsToAction as cta, index}
							<Button 
								class="w-full transform transition-all duration-300 hover:scale-105 md:w-auto" 
								href={cta.href} 
								variant={cta.variant || "primary"}
								size="lg"
								suffix={index === 0 ? IconArrowRight : index === 1 ? IconBookOpen : undefined}
							>
								{cta.label}
							</Button>
						{/each}
					</div>
				</div>
			</div>
			<img
				src={imageSrc}
				alt="Successful academic researcher in modern office celebrating breakthrough discovery with raised hands, showing the satisfaction and joy of efficient research"
				class="hidden aspect-[4/5] size-full max-h-full w-full rounded-[calc(max(var(--inner-radius),.25rem))] object-cover transition-transform duration-500 hover:scale-105 lg:block"
			/>
		</div>
	</section>
</div>

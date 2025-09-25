<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
		{
			title: "Speed of discovery",
			description: "We believe breakthrough research shouldn't be slowed by tedious paper searches. Our tools are built for the pace of scientific inquiry."
		},
		{
			title: "Accessible knowledge",
			description: "Complex graph databases and AI-powered insights should be intuitive for every researcher, regardless of technical background."
		},
		{
			title: "Research integrity",
			description: "We support the scientific method by making it easier to find, verify, and build upon existing research with complete transparency."
		}
	];
</script>

<SecondaryHero
	title="Think faster than you read"
	subtitle="The research browser built for breakthroughs"
	imageSrc="/generated/image-a-group-of-diverse-researchers-collabora.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"We started in 2018 with a simple goal: make helpful tech that people actually need. While many chase profits, we chose to do things differently.",
		"Beyond making good products, we care about doing the right thing, being kind to our planet, and making sure everyone can use what we build. That's our compass.",
		"From day one, we've asked ourselves: 'Does this actually help people?' This question gets us through tough calls and shapes who we are. We're playing the long game here.",
		"We think about how our work affects real people's lives. We build tech that brings people together, keeps your information safe, and treats everyone fairly. When we stick to these basics, good things happen."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Our team."
	subtitle="Building the future of research navigation."
	stakeholders={[
		{
			name: "Veronica Chambers",
			position: "Founder & Factotum",
			bio: "Passionate about making complex research accessible to everyone through intuitive AI-powered tools.",
			image: "/generated/image-professional-headshot-of-a-woman-scienti.webp"
		}
	]}
/>

<!-- CTA Section -->
<CallToAction
	title="Ready to accelerate your research?"
	subtitle="Start discovering connections faster"
	description="Join researchers worldwide who have transformed their literature review process. Stop spending hours searching and start making breakthrough discoveries with AI-powered paper navigation."
	imageSrc="/generated/image-a-joyful-female-researcher-in-a-modern-w.webp"
	callsToAction={[
		{
			href: "/",
			label: "Try Surf arXiv",
			variant: "primary"
		},
		{
			href: "/about",
			label: "See how it works",
			variant: "secondary"
		}
	]}
/>

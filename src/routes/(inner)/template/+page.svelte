<script lang="ts">
	import DocsShell from '$docs/layouts/DocsShell/DocsShell.svelte';
	import { DocsFeature, type DocsShellSettings } from '$docs/layouts/DocsShell/types';
	import DocsPreview from '$docs/components/DocsPreview/DocsPreview.svelte';
	// Utilities
	import CodeBlock from '$lib/utilities/CodeBlock/CodeBlock.svelte';
	// Sveld
	// import sveldComp from '$lib/.../Component.svelte?raw&sveld';

	// Docs Shell
	const settings: DocsShellSettings = {
		feature: DocsFeature.Component,
		name: 'Template',
		description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
		imports: ['Template'],
		types: ['Template'],
		stylesheetIncludes: ['all', 'elements'],
		stylesheets: ['elements/template'],
		source: 'components/Template',
		aria: 'https://www.w3.org/WAI/ARIA/apg/'
		// dependencies: [{ label: 'Highlight.js', url: 'https://highlightjs.org/' }],
		// components: [{sveld: sveldComp}],
		// classes: [
		// 	['<code>.foo</code>', '-', '...'],
		// 	['<code>.bar</code>', '-', '...']
		// ],
		// keyboard: [
		// 	['<code>foo</code>', '-', '-', '-', '...'],
		// 	['<code>bar</code>', '-', '-', '-', '...']
		// ]
	};
</script>

<DocsShell {settings}>
	<!-- Slot: Sandbox -->
	<svelte:fragment slot="sandbox">
		<DocsPreview>
			<svelte:fragment slot="preview">
				<p>(feature)</p>
			</svelte:fragment>
			<svelte:fragment slot="source">
				<CodeBlock language="html" code={`(code snippet)`} />
			</svelte:fragment>
		</DocsPreview>
	</svelte:fragment>

	<!-- Slot: Usage -->
	<svelte:fragment slot="usage">
		<section class="space-y-4">
			<h2>Title 1</h2>
			<p>Describe how to use the feature.</p>
			<CodeBlock language="html" code={`(code)`} />
		</section>
		<section class="space-y-4">
			<h2>Title 2</h2>
			<p>Describe how to use the feature.</p>
			<CodeBlock language="html" code={`(code)`} />
		</section>
	</svelte:fragment>
</DocsShell>

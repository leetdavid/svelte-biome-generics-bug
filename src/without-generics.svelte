<script lang="ts">
import type { SomeType } from "./types.ts";

// biome-ignore lint/correctness/noUnusedVariables: Biome currently doesn't recognize that item is used. Out of scope for this repo.
let { item }: { item: SomeType } = $props();
</script>

<div>{item.label}</div>

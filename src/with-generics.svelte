<script lang="ts" generics="T extends Record<string, unknown>">
import type { SomeType } from "./types.ts";

let { value, item }: { value: T; item: SomeType } = $props();
</script>

<div>{JSON.stringify(value)} - {item.label}</div>

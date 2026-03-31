# svelte-biome-generics-bug

This is a minimal reproduction of a bug in Biome, where using `generics` in `<script>` causes the content in script to not be recognized as Typescript.

### Linting Error

The error is available in the [GitHub action](https://github.com/leetdavid/svelte-biome-generics-bug/actions/runs/23779414587/job/69288471749) in this repo.

Output:
```
src/with-generics.svelte:1:62 parse ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × unterminated string literal
  
> svelte-biome-generics-bug@1.0.0 lint /home/runner/work/svelte-biome-generics-bug/svelte-biome-generics-bug
> biome lint

  > 1 │ <script lang="ts" generics="T extends Record<string, unknown>">
Checked 3 files in 2ms. No fixes applied.
Found 3 errors.
      │                                                              ^^
    2 │ import type { SomeType } from "./types.ts";
    3 │ 
  
  i 
  
  > 1 │ <script lang="ts" generics="T extends Record<string, unknown>">
      │ ^^
    2 │ import type { SomeType } from "./types.ts";
    3 │ 
  
  i The closing quote must be on the same line.
  

src/with-generics.svelte:2:8 parse ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × 'import type' are a TypeScript only feature. Convert your file to a TypeScript file or remove the syntax.
  
    1 │ <script lang="ts" generics="T extends Record<string, unknown>">
  > 2 │ import type { SomeType } from "./types.ts";
      │        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    3 │ 
    4 │ let { value, item }: { value: T; item: SomeType } = $props();
  
  i TypeScript only syntax
  

src/with-generics.svelte:4:20 parse ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × type annotation are a TypeScript only feature. Convert your file to a TypeScript file or remove the syntax.
  
    2 │ import type { SomeType } from "./types.ts";
    3 │ 
  > 4 │ let { value, item }: { value: T; item: SomeType } = $props();
      │                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    5 │ </script>
    6 │ 
  
  i TypeScript only syntax
  

lint ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Some errors were emitted while running checks.

```


### Environment Information

`biome rage` output:
```
CLI:
  Version:                      2.4.10
  Color support:                true

Platform:
  CPU Architecture:             aarch64
  OS:                           macos

Environment:
  BIOME_LOG_PATH:                    unset
  BIOME_LOG_PREFIX_NAME:             unset
  BIOME_LOG_LEVEL:                   unset
  BIOME_LOG_KIND:                    unset
  BIOME_CONFIG_PATH:                 unset
  BIOME_THREADS:                     unset
  BIOME_WATCHER_KIND:                unset
  BIOME_WATCHER_POLLING_INTERVAL:    unset
  NO_COLOR:                     unset
  TERM:                         xterm-256color
  JS_RUNTIME_VERSION:           v24.11.0
  JS_RUNTIME_NAME:              node
  NODE_PACKAGE_MANAGER:         pnpm/10.12.4

Biome Configuration:
  Status:                       Loaded successfully
  Path:                         biome.json
  Formatter enabled:            true
  Linter enabled:               true
  Assist enabled:               true
  VCS enabled:                  false
  HTML full support enabled:    unset

Workspace:
  Open Documents:               0
```

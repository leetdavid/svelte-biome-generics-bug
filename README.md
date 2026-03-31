# svelte-biome-generics-bug

This is a minimal reproduction of a bug in Biome, where using `generics` in `<script>` causes the content in script to not be recognized as Typescript.

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

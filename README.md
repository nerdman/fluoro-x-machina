# fluoro-x-machina

A rough attempt to port my favorite Neovim theme [Fluoromachine](https://github.com/maxmx03/fluoromachine.nvim) to a [Shiki Syntax Highlighter](https://shiki.style/guide/load-theme) textmate grammar.

How to add to astro.config.mjs
```js {6,13} 
import { defineConfig } from "astro/config";
import mdx from "@astrojs/mdx";
import sitemap from "@astrojs/sitemap";
import { transformerCopyButton } from "@rehype-pretty/transformers";

import fluoroxmachina from "./fluoro-x-machina.json";

export default defineConfig({
  site: "https://example.com",
  integrations: [mdx(), sitemap()],
  markdown: {
    shikiConfig: {
      theme: fluoroxmachina,
      wrap: true,
      transformers: [
        transformerCopyButton({
          visibility: "always",
          feedbackDuration: 3_000,
        }),
      ],
    },
  },
});

```

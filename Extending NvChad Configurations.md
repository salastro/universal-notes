#linux #nvim #nvchad
If you are using nvchad (v2.0) and want to extend configuration, load the original configuration and change its values, then—in case of overrides—return the new configuration.
Example (in overrides):
```lua
M.cmp = function()
  local cmp = require "cmp" -- use cmp
  local conf = require "plugins.configs.cmp" -- load default configuration
  conf.mapping = { -- change maps
    ["<CR>"] = cmp.config.disable,
    ["<C-p>"] = cmp.mapping.select_prev_item(),
    ["<C-n>"] = cmp.mapping.select_next_item(),
    ["<C-d>"] = cmp.mapping.scroll_docs(-4),
    ["<C-f>"] = cmp.mapping.scroll_docs(4),
	-- rest of the config
  }
  conf.sources = { -- change sources
    { name = "nvim_lsp" },
    { name = "luasnip" },
    { name = "buffer" },
    { name = "nvim_lua" },
    { name = "async_path" },
    { name = "digraphs" },
  }
  return conf -- return result
end
```
Example (in configs):
```lua
-- Default configuration for Luasnip
require("plugins.configs.others").luasnip {
  history = false,
  updateevents = "TextChanged,TextChangedI",
  enable_autosnippets = true,
}

-- Define path
local path = vim.fn.stdpath "config" .. "/lua/custom/snippets"

-- Loop through all files in the path
for _, file in ipairs(vim.fn.readdir(path)) do
  -- Extract type and snippets
  local filetype = vim.fn.fnamemodify(file, ":t:r")
  local snippets = require("custom.snippets." .. filetype)
  require("luasnip").add_snippets(filetype, snippets, { default_priority = 1001 })
end

-- there is no return since this is directly sourced in plugins.lua

```
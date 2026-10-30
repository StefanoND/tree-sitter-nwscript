Add this somewhere before your treesitter setup. You may now install with "TSInstall nwscript"

```C++
vim.api.nvim_create_autocmd("User", {
  pattern = "TSUpdate",
  callback = function()
    require("nvim-treesitter.parsers").nwscript = {
      install_info = {
        url = "https://github.com/StefanoND/tree-sitter-nwscript",
        revision = "ebafc659d634881bff8feb4b6cd35bf70e904e33", -- commit hash for revision to check out; HEAD if missing
        generate = false, -- only needed if repo does not contain pre-generated `src/parser.c`
        generate_from_json = false, -- only needed if repo does not contain `src/grammar.json` either
        queries = "queries", -- also install queries from given directory
      },
      -- tier = 1,
    }
  end,
})
```

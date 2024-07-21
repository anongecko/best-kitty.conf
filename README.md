# best-kitty.conf

**The best - and only - kitty.conf you'll ever need for a blissful macOS terminal experience.**

This kitty.conf is meticulously crafted to provide a streamlined and efficient terminal experience on macOS. Unlike other configurations that overcomplicate things with unnecessary files, themes, and convoluted keybindings, this configuration is designed with simplicity and common sense in mind. It leverages Kitty's built-in features, such as the theme switcher, to avoid unnecessary modifications.

This configuration empowers you to control every aspect of your terminal workflow using only your keyboard. No mouse required. It strikes the perfect balance between customization and minimalism, ensuring that all essential keybindings are intuitive and readily available.

## Features

- **Clean and concise:** No complex file tree or obscure settings.
- **Intuitive keybindings:** Uses common sense shortcuts for all essential actions.
- **Keyboard-centric workflow:** Designed for power users who prefer keyboard navigation.
- **Leverages built-in features:** Utilizes Kitty's theme switcher and other native functionalities.
- **No unnecessary modifications:** Keeps the configuration clean and focused.

## Installation

### Mac (Preferred)

1. Open Kitty and run the following command to download the configuration file:

   ```sh
   curl -o ~/.config/kitty/kitty.conf https://raw.githubusercontent.com/your-username/best-kitty.conf/main/kitty.conf
   ```

2. Reload the configuration file by pressing `ctrl+shift+f5`.

### Windows

1. Open Kitty and run the following command to download the configuration file:

   ```sh
   curl -o "%APPDATA%\kitty\kitty.conf" https://raw.githubusercontent.com/your-username/best-kitty.conf/main/kitty.conf
   ```

2. Reload the configuration file by pressing `ctrl+shift+f5`.

### Linux

1. Open Kitty and run the following command to download the configuration file:

   ```sh
   curl -o ~/.config/kitty/kitty.conf https://raw.githubusercontent.com/your-username/best-kitty.conf/main/kitty.conf
   ```

2. Reload the configuration file by pressing `ctrl+shift+f5`.

## NvChad Integration

To ensure proper integration with NvChad, add the following to your `chadrc.lua` file located in the `~/.config/nvim/lua/custom/` directory:

```lua
local M = {}

M.mappings = {
  normal_mode = {
    -- Your custom normal mode mappings here
  },
  insert_mode = {
    -- Your custom insert mode mappings here
  },
  visual_mode = {
    -- Your custom visual mode mappings here
  },
}

-- Set environment variable when Neovim starts or resumes
vim.api.nvim_create_autocmd({ "VimEnter", "VimResume" }, {
  group = vim.api.nvim_create_augroup("KittyIntegration", { clear = true }),
  callback = function()
    io.stdout:write("\x1b]1337;SetUserVar=IN_EDITOR=MQo\007")
  end,
})

-- Unset environment variable when Neovim loses focus
vim.api.nvim_create_autocmd({ "VimLeave", "VimSuspend" }, {
  group = vim.api.nvim_create_augroup("KittyUnsetVarVimLeave", { clear = true }),
  callback = function()
    io.stdout:write("\x1b]1337;SetUserVar=IN_EDITOR\007")
  end,
})

return M
```

## License

MIT

## Buy Me a Coffee (XMR) ;D

8AF7ys7QcvLCmXNVR2GkH6GnaBxhafW7eBTy9JLKLnXxdyisKvkWdVv3hdfu2NgrsiMWgif5VJDDsbbkBj5xtMu9RwUVZsz

## Contact Me

anongecko@tutamail.com

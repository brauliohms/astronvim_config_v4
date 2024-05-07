# AstroNvim Template

**NOTE:** This is for AstroNvim v4+

A template for getting started with [AstroNvim](https://github.com/AstroNvim/AstroNvim)

## 🛠️ Installation

### Install Dependencies

`sudo apt install npm python3 python3-pip python3-venv`

#### Make a backup of your current nvim and shared folder

```bash
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak
```

### Install NeoVim from source

#### Remove old Neovim from system

```bash
sudo apt remove neovim --purge
sudo apt autoremove autoclean clean
```

#### Install Neovim Dependencies

```bash
sudo apt update
sudo apt install git build-essential cmake git pkg-config libtool g++ libunibilium4 libunibilium-dev \
ninja-build gettext libtool libtool-bin autoconf automake unzip curl doxygen lua-term lua-term-dev luarocks
```

#### Build Neovim from source code

```bash
git clone https://github.com/neovim/neovim
cd neovim
make CMAKE_BUILD_TYPE=RelWithDebInfo
sudo make install
```

> credits: `https://terminalroot.com.br/2022/05/como-compilar-o-neovim-do-zero.html`

### Install NerdFonts

```bash
git clone --depth=1 https://github.com/terroo/fonts fonts
mv fonts/fonts ~/.local/share
fc-cache -fv
rm -r fonts
```

#### Create a new user repository from this template

Press the "Use this template" button above to create a new repository to store your user configuration.

You can also just clone this repository directly if you do not want to track your user configuration in GitHub.

#### Install AstroNvim with my configurations

```bash
git clone https://github.com/brauliohms/astronvim_config_v4 ~/.config/nvim
```

#### Create Alias

`echo "alias vi='nvim'" >> ~/.bash_aliases`
`echo "alias vim='nvim'" >> ~/.bash_aliases`

#### Start Neovim

```bash
nvim
```

#### Settings for Pyhton

After first install, coment in `lua/community.lua`:
`{ import = "astrocommunity.pack.python" },`

and install if not installed in Mason(type `:Mason`), the packages:
`ast-grep, autoflake, autopep8, black, debugpy, flake8, isort, python-lsp-server, ruff-lsp`

and remove `pyright`

> In Mason find the package and select and:
> to install -> press `i` (lowercase)
> to uninstall -> press `X` (uppercase)

#### Configure pycodestyle

create `~/.config/pycodestyle`

```sh
[pycodestyle]
ignore = E501, W503, W504
```

# Setup wsl para desenvolvimento


### 1- Instalando o zsh

Primeiro instale o zsh

```
sudo apt install zsh
```
Cole o comando no terminal e siga com a instalação

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 2- Instalando o Spaceship

Clone o repositório do tema

```
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

Faça um link simbólico do tema na pasta do zsh.

```
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Abra o ~/.zshrc com o editor de sua preferência e edite o tema para :

```
ZSH_THEME="spaceship"
```

Neste mesmo arquivo, adicione as opções para desabilitar algumas das funções que consomem desempenho e fazer outras customizações.

```
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  node          # node version
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)
SPACESHIP_USER_SHOW=always
SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SUFFIX=" "
```

Procure no ~/.zshrc a parte dos plugins e adicione os seguintes:

```
plugins=(git nvm sudo web-search copypath history)
```

Reinicie o terminal para ver a mudança.

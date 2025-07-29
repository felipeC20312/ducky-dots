# ducky-dots

Repositório de dotfiles para backup e versionamento das configurações de sistema.  
Este projeto centraliza os arquivos de configuração do ambiente Unix/Linux, tornando fácil restaurar, replicar ou sincronizar o setup em diferentes máquinas.

---

## Estrutura

```
ducky-dots/
├── .zshrc           # Configuração do Zsh
├── .zsh/            # Funções e helpers para o shell
├── .bashrc          # Fallback Bash
├── .profile         # Variáveis de ambiente e init geral
├── .config/         # Configurações de programas (Neovim, Git, etc)
├── update-dots.zsh  # Script de backup e git update
└── README.md        # Este arquivo
```

---

## Objetivo

- Manter um ambiente shell consistente
- Automatizar backups de configurações
- Versionar o setup de forma segura com Git
- Tornar fácil a replicação do ambiente em qualquer host

---

## Uso

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/ducky-dots.git ~/ducky-dots
cd ~/ducky-dots
```

### Atualizando o backup dos arquivos de configuração:

```zsh
source ./update-dots.zsh
update-dots
```

Esse comando irá:

- Criar um diretório `.backup` caso não exista
- Copiar os arquivos definidos no array de backup
- Exibir logs de status de cada operação
- Perguntar se deseja fazer commit das alterações no Git

---

## Alias útil para o `.zshrc`

```zsh
alias backup-dots="source ~/ducky-dots/update-dots.zsh && update-dots"
```

---

## Segurança

**Nunca adicione senhas, chaves privadas ou tokens ao repositório.**  
Utilize `.gitignore`, `gpg`, `git-crypt`, ou um cofre seguro para lidar com dados sensíveis.

---

## Requisitos

- Zsh
- Git
- Linux ou macOS

---

## Links úteis

- [dotfiles.github.io](https://dotfiles.github.io/)
- [Zsh wiki](https://github.com/ohmyzsh/ohmyzsh/wiki)
- [The Art of Command Line](https://github.com/jlevy/the-art-of-command-line)

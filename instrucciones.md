# Configuración para tunear mi terminal

## Instalación de ZSH

El presente documento tiene como objetivo presentar los comandos utilizados para tunear mi terminal, usando `zsh` como bash y `oh-my-zsh`.

Lo primero es instalar zsh, con la siguiente instrucción.

```
sudo apt install zsh
```
seguido, realizamos el cambio de shell.

``` 
chsh -s $(which zsh)
```
Es necesario cerrar sesión y volver a iniciarla para que se vea reflejado el cambio de shell. Al iniciar la terminal pedira crear el archivo `.zshrc` por lo que la opción 0 es la indicada para tener el archivo creado y sin contenido.

## Instalación de Oh my zsh

Es necesario tener *Git* y *curl* instalados para poder hacer la instalación. Para instalar oh-my-zsh, ejecutar:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
lo que instalará oh my zsh y modificará el archivo `.zshrc` para una configuración inicial.

agregando plugins. ejecutar las siguientes líneas.

```
cd .oh-my-zsh/custom/plugins/
git clone https://github.com/zsh-users/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
```
agregar al archivo `.zshrc`````, lo siguiente en el apartado plugins.

```
plugins=(
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
 ) 
```

## Instalando Alias

Lo primero es instalar una fuente de [NerdFonts](https://www.nerdfonts.com/), probé con FiraCode pero no me gustó, dejaremos JetBrainsMono.

para sistemas ubuntu, ejecutar:

```
wget -P ~/.local/share/fonts https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/JetBrainsMono.zip \
&& cd ~/.local/share/fonts \
&& unzip JetBrainsMono.zip \
&& rm JetBrainsMono.zip \
&& fc-cache -fv
```

Es necesario instalar el paquete *eza* para tener una versión mejorada de *ls*

```
sudo apt install eza
```

y definir los alias correspondientes en el archivo `.zshrc`

```
alias ls="eza --icons --color=always --group-directories-first"
```


## Instalando Starship



y configurarla en las *Preferencias* de la terminal. Seguido de esto instalamos *starship* de la página de [Starship](https://starship.rs/), ejecutando:

```
curl -sS https://starship.rs/install.sh | sh
```

Y agregamos al final del archivo `.zshrc` lo siguiente:

```
eval "$(starship init zsh)"
```











































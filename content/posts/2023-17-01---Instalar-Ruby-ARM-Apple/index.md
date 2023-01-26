---
title: Cómo instalar la versión más reciente de Ruby en M1/M1 Pro/M1 Max y M2/M2 Pro/M2 Max Mac OS Ventura
date: "2023-01-17T21:06:32.169Z"
template: "post"
draft: false
slug: "/posts/mis-primeros-pasos"
category: "Personal"
tags:
  - "Macbook"
  - "Ruby"
  - "Web Development"
  - "M1"
  - "M2"
  - "rbenv"
description: "En este artículo te mostraré de manera rápida como instalar la ultima versión de Ruby utilizando rbenv, en tu macbook con procesador M1/M1 Pro/M1 Max y M2/M2 Pro/M2"
socialImage: "./media/m2.jpg"
---

<!-- Es difícil empezar, y es aun más difícil con un hijo en camino, 17 años, estudiante y sin un empleo. Fue duro, más no imposible. Te cuento un poco de mi trayectoria y el como llegue de ser un estudiante de preparatoria a convertirme en el lider técnico de una empresa de software." -->

Mac OS Ventura tiene instalado por defecto Ruby pero la versión 2.6, si requerimos instalar la versión más reciente o algúna versión en especifico lo recomendado es utilizar algun manejador de versiones como rvm o rbenv.

En esta ocación te mostrare como instalar y utilizar la herramienta rbenv, para esto requerimos tener instalado en nuestra computadora el gestor de paquetes [brew](https://brew.sh/index_es)

Para instalar brew requerimos ejecutar en nuestra terminal el siguiente comando

## Instalar brew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Una vez instalado brew podemos proceder a instalar la herramienta [rbenv](https://github.com/rbenv/rbenv), para esto ejecutamos los siguientes comandos.

## Instalar rbenv

```

# Install rbenv
brew install rbenv

# Initialise rbenv
rbenv init


```

## Verificar instalación de rbenv

Ejecutamos el siguiente comando

```

curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash


```

Nos tendrá que devolver lo siguiente:

```

staller/raw/main/bin/rbenv-doctor | bash
Checking for `rbenv' in PATH: /opt/homebrew/bin/rbenv
Checking for rbenv shims in PATH: OK
Checking `rbenv install' support: /opt/homebrew/bin/rbenv-install (ruby-build 20221225)
Counting installed Ruby versions: 1 versions
Auditing installed plugins: OK


```

Una vez validada la instalación de rbenv procedemos a configurar nuestra terminal para que detecte la versión instalada con rbenv como la versión por defecto.

Para esto ejecutamos alguno de los siguientes comandos (Depende que shell tengas instalada en tu computadora)

```
# ZSH
vi ~/.zshrc

# Bash
vi ~/.bash_profile

```

En este archivo nos desplazaremos hasta el final y pegaremos lo siguiente:

```
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init - zsh)"

```

Guardamos los cambios y enseguida ejecutamos el siguiente comando:

```
# ZSH
source ~/.zshrc

# Bash
source ~/.bash_profile

```

Ya con esto tendremos configurado nuestro manejador de versiones de Ruby.

Ahora ya solo queda instalar la versión que deseemos, para listar las versiones disponibles ejecutamos el siguiente comando:

```
rbenv install -l

2.7.7
3.0.5
3.1.3
3.2.0
jruby-9.4.0.0
mruby-3.1.0
picoruby-3.0.0
rbx-5.0
truffleruby-22.3.0
truffleruby+graalvm-22.3.0

Only latest stable releases for each Ruby implementation are shown.
Use 'rbenv install --list-all / -L' to show all local versions.

```

Nos mostrará todas las versiones disponibles. Una vez localizada la versión a instalar ejecutamos el siguiente comando (En mi caso instalare la versión 3.1.3):

```
rbenv install 3.1.3

```

Una vez que finalice la instalación procedemos setear la versión global:

```
rbenv global 3.1.3

```

Con esto ya estaría seteada la versión que acabamos de instalar, para vereficar la versión de nuestro sistema ejecutamos el siguiente comando:

```
ruby -v

ruby 3.1.3p185 (2022-11-24 revision 1a6b16756e) [arm64-darwin22]

```

Ya con esto hemos finalizado la instalación de Ruby en un procesados ARM de Apple. Espero que te haya funcionado correctamente, me decidí a realizar este pequeño articulo ya que fue muy difícil la instalación de Ruby en mi Mac M2. Saludos...

---
title: How to install the latest ruby version on M1/M1 Pro/M1 Max y M2/M2 Pro/M2 Max Mac OS Ventura
date: "2023-01-17T21:06:32.169Z"
template: "post"
draft: false
slug: "/posts/install-ruby-arm-apple"
category: "Ruby"
tags:
  - "Macbook"
  - "Ruby"
  - "Web Development"
  - "M1"
  - "M2"
  - "rbenv"
description: "In this article, I will quickly show you how to install the latest version of Ruby using rbenv on your MacBook with processor M1/M1 Pro/M1 Max y M2/M2 Pro/M2"
socialImage: "./media/m2.jpg"
---

Mac OS Ventura comes with Ruby pre-installed, but it is version 2.6. If you need to install a specific or newer version, it is recommended to use a version manager like rvm or rbenv.

In this tutorial, we will show you how to install and use the rbenv tool. To do this, you will need to have the package manager, Homebrew, installed on your computer.

First, install Homebrew by running the following command in your terminal:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Once Homebrew is installed, you can proceed to install rbenv by running the following commands:

```
brew install rbenv
rbenv init
```

To verify that rbenv is installed correctly, run the following command:

```
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash

```

This should return the following output:

```
Checking for `rbenv' in PATH: /opt/homebrew/bin/rbenv
Checking for rbenv shims in PATH: OK
Checking `rbenv install' support: /opt/homebrew/bin/rbenv-install (ruby-build 20221225)
Counting installed Ruby versions: 1 versions
Auditing installed plugins: OK
```

Next, configure your terminal to use the version of Ruby installed with rbenv as the default. To do this, open your shell profile file (e.g., ~/.zshrc or ~/.bash_profile) and add the following lines at the end:

```
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init - zsh)"
```

Save the changes and then run the following command to reload your shell profile:

```
source ~/.zshrc
```

Now, you can install the version of Ruby you need. To see a list of available versions, run the following command:

```
rbenv install -l
```

To install a specific version, for example 3.1.3, run the command:

```
rbenv install 3.1.3
```

Finally, set the newly installed version as the global version:

```
rbenv global 3.1.3
```

You can check the version of Ruby installed by running:

```
ruby -v
```

With these steps, you should now have Ruby successfully installed on an ARM-based Apple device. If you have any issues, please let me know.

# How to Beautify Your Terminal

There are many terminal tools out there to modify your prompt in the command line! :computer:

Some are frameworks to manage your teminal configuration, like :rainbow: [oh-my-zsh](https://ohmyz.sh/), which you can add plugins, helper functions, themes, autocompletion etc.

Others, like :rocket: [starship](https://starship.rs/) are customization prompts.

In this guide, we're going to install `starship` to beautify our terminal!

## A little about Starship

**Starship** is a minimal and super fast prompt for any shell! :sparkle: It's very easy to install and implement, with a variety of set themes ready to go. Every detail is customizable to make it as minimal or feature-rich as you'd like it to be.

## Getting Started

:dizzy: First, to the ["Get Started" guide](https://starship.rs/guide/)!

### Prerequisite

A prerequisite is to have a :nerd_face: [Nerd Font](https://www.nerdfonts.com/) installed and enabled in your terminal. You can do download one, many, or all [directly](https://www.nerdfonts.com/font-downloads) from Nerd Fonts, or use a package manager like [Homebrew](https://brew.sh/) for  macOS and Winget or [Chocolatey](https://chocolatey.org/) for :window: Windows.

If using **Homebrew**...\*

<details closed>
<summary> And you want <i>ALL</i> the fonts: </summary>

```shell
brew tap homebrew/cask-fonts
brew search '/font-.*-nerd-font/' | awk '{ print $1 }' | xargs -I{} brew install --cask {} || true
```

</details>

<details>
<summary> Or you prefer to <i>explicitly list</i> the fonts you want to install: </summary>

```shell
#!/bin/bash

fonts_list=(
  font-3270-nerd-font
  font-fira-mono-nerd-font
  font-inconsolata-go-nerd-font
  font-inconsolata-lgc-nerd-font
  font-inconsolata-nerd-font
  font-monofur-nerd-font
  font-overpass-nerd-font
  font-ubuntu-mono-nerd-font
  font-agave-nerd-font
  font-arimo-nerd-font
  font-anonymice-nerd-font
  font-aurulent-sans-mono-nerd-font
  font-bigblue-terminal-nerd-font
  font-bitstream-vera-sans-mono-nerd-font
  font-blex-mono-nerd-font
  font-caskaydia-cove-nerd-font
  font-code-new-roman-nerd-font
  font-cousine-nerd-font
  font-daddy-time-mono-nerd-font
  font-dejavu-sans-mono-nerd-font
  font-droid-sans-mono-nerd-font
  font-fantasque-sans-mono-nerd-font
  font-fira-code-nerd-font
  font-go-mono-nerd-font
  font-gohufont-nerd-font
  font-hack-nerd-font
  font-hasklug-nerd-font
  font-heavy-data-nerd-font
  font-hurmit-nerd-font
  font-im-writing-nerd-font
  font-iosevka-nerd-font
  font-jetbrains-mono-nerd-font
  font-lekton-nerd-font
  font-liberation-nerd-font
  font-meslo-lg-nerd-font
  font-monoid-nerd-font
  font-mononoki-nerd-font
  font-mplus-nerd-font
  font-noto-nerd-font
  font-open-dyslexic-nerd-font
  font-profont-nerd-font
  font-proggy-clean-tt-nerd-font
  font-roboto-mono-nerd-font
  font-sauce-code-pro-nerd-font
  font-shure-tech-mono-nerd-font
  font-space-mono-nerd-font
  font-terminess-ttf-nerd-font
  font-tinos-nerd-font
  font-ubuntu-nerd-font
  font-victor-mono-nerd-font
)

brew tap homebrew/cask-fonts

for font in "${fonts_list[@]}"
do
  brew install --cask "$font"
done
exit
```

</details>

<br>

\*Solutions from [this](https://gist.github.com/davidteren/898f2dcccd42d9f8680ec69a3a5d350e) Gist

## Installation

#### 1. [Install](https://starship.rs/guide/#step-1-install-starship) the latest version of **Starship** according to your OS

If using a package manager, continue to do so:

- **macOS** w/ Homebrew:

  ```
  brew install starship
  ```

- **Windows** w/ Chocolatey:

  ```
  choco install starship
  ```

#### 2. [Set up your shell](https://starship.rs/guide/#step-2-set-up-your-shell-to-use-starship) to use Starship

- MacOS → Zsh
- Windows → Bash

From the root directory (`cd ~` to get there), check if you have a `.zshrc` or `.bashrc` file:

```
ls -a
```

If you don't see it listed, create one: `touch .zshrc` or `touch .bashrc`. Then open the file (`code .zshrc` or `code .bashrc`) to edit it:

- **Zsh**:
  Add the following to the end of `~/.zshrc`:

  ```
  eval "$(starship init bash)"
  ```

- **Bash**:
  Add the following to the end of `~/.bashrc`:
  ```
  eval "$(starship init bash)"
  ```

#### 3. [Configure](https://starship.rs/guide/#step-3-configure-starship) Starship!

Close and restart your terminal.

You should see a beautiful new shell prompt! If you're happy with the defaults, enjoy! :sparkles:

To further customize Starship:

- Learn how to [configure](https://starship.rs/config/) Starship to your liking
- Use a [preset](https://starship.rs/presets/) built by others

I'm using the [Tokyo Night](https://starship.rs/presets/tokyo-night) preset configuration with a few tweaks I made to the config file.

To use Tokyo Night out of the box, execute the following in your terminal:
```
starship preset tokyo-night -o ~/.config/starship.toml
```

It will change the `~./config/starship.toml` to the preset configurations.

If you'd like to make tweaks to presets, open the config file and make your changes! 

```
code ~/.config/starship.toml
```

### That's it! :smiley: Have fun! :star:
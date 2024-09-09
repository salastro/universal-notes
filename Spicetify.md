Spicetify is a cli tool that modifies [[|Spotify]] desktop functionality and interface. 
## Installation
https://spicetify.app/docs/getting-started/
```sh
curl -fsSL https://raw.githubusercontent.com/spicetify/cli/main/install.sh | sh
```
## Basic Usage
```sh
spicetify backup apply enable-devtools
```
## Themes
1. Install themes (https://github.com/spicetify/spicetify-themes) into `~/.config/spicetify/Themes/`
2. 
```sh
spicetify config current-theme text
spicetify apply		
```
## Extensions
Path: `~/.config/spicetify/Extensions`
List: https://spicetify.app/docs/advanced-usage/extensions
Run:
```sh
spicetify config extensions fullAppDisplay.js # change the file name to the extension you want
spicetify apply
```
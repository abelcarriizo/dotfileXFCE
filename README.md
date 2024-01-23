***Language***
- [🇪🇸 Español](./README.es.md)
- 🇺🇸 English

# My First Dotfiles

## Table of Contents
- [Previews](#previews)
- [Clone Repository](#clone-repository)
- [Initial Installation](#initial-installation)
  - [Change Theme, Icons, Fonts, etc.](#change-theme-icons-fonts-etc)
  - [LightDM Configuration](#lightdm-configuration)
- [Picom Installation](#picom-installation)
  - [Dependencies](#dependencies)
  - [Start Picom](#start-picom)
- [Install and Customize Neofetch](#install-and-customize-neofetch)


## Previews
![Main Preview](previews/main_preview.png)
![Window Preview](previews/window_preview.png)

## Clone Repository
To clone this repository to your home directory, use the following command:

```bash
git clone https://github.com/abelcarriizo/dotfileXFCE.git ~/dotfiles
```

## Initial Installation

```bash
sudo apt install mughshot xfce4-terminal
```

Set xfce4-terminal as the default terminal: Settings -> Default Applications.

```bash
sudo apt install qt5-style-kvantum qt5-style-kvantum-themes
```

> [!CAUTION]
> The folder structure in the repository reflects the expected structure in your home directory. You should copy or cut the contents of the repository and paste it directly into your home directory (`/home/your_user`).

### Change Theme, Icons, Fonts, etc.

Access the Settings application and follow these steps:

#### Theme
1. **Appearance -> Style:** Everblush_GTK_THEME

#### Icons
2. **Appearance -> Icons:** Zafiro-icons-Dark

#### Font
3. **Appearance -> Fonts:**
   - Default font: Iosevka Nerd Font Regular, size 10
   - Default monospace font: JetbrainsMono Nerd Font Mono Regular, size 10

#### Window Manager
4. **Window Manager:**
   - Theme: Everblush-xfwm
   - Title font: Iosevka Nerd Font Regular, size 9
   - Title alignment: Left

#### Mouse and Touchpad
5. **Mouse and Touchpad:**
   - Theme: Radioactive-nord

#### Kvantum Manager
6. **Kvantum Manager:**
   - Change/Delete theme: Select Everblush theme

> [!NOTE]
> Logout to see the changes.

### LightDM Configuration

1. Go to the `~/.themes` directory and run:

```bash
sudo cp -R Everblush /usr/share/themes
```

2. Go to the following directory and run:

```bash
sudo cp -R Zafiro-Icons-* /usr/share/icons/
sudo cp -R Papirus* /usr/share/icons/
```

3. Open the "GTK+ Interface Configuration" application from the menu and select:
   - Theme: Everblush
   - Icons: Papirus-Dark 
   - Font: Noto Sans Regular 10
   - Wallpaper:
      - Color: #232a2d

> [!NOTE]
> Logout to see the changes.

### Picom Installation

#### Dependencies

```bash
sudo apt install libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-randr0-dev libxcb-composite0-dev libxcb-image0-dev libxcb-present-dev libxcb-xinerama0-dev libxcb-glx0-dev libpixman-1-dev libdbus-1-dev libconfig-dev libgl1-mesa-dev libpcre2-dev libpcre3-dev libevdev-dev uthash-dev libev-dev libx11-xcb-dev meson libxcb-util1 libxcb-util-dev libxcb-dpms0 libxcb-dpms0-dev
```

Clone the Picom repository in your preferred directory (e.g., `~/Downloads`):

```bash
git clone https://github.com/yshui/picom
```

Run the following commands to compile and install:

```bash
cd ~/Downloads/picom
git submodule update --init --recursive
meson --buildtype=release . build
ninja -C build
ninja -C build install
```

Disable the current compositor in "Settings" -> "Window Manager Tweaks" -> "Compositor" and uncheck "Enable display compositing."

#### Start Picom

Add Picom to the system startup:
   - Name: Picom Startup
   - Description: Picom Compositor
   - Command: picom
   - Trigger: On login

> [!NOTE]
> Logout to see the changes.

### Install and Customize Neofetch
Let's proceed with the final part:

To install Neofetch, use the following command:

```bash
sudo apt install neofetch
```

Now, let's customize the Neofetch configuration. Access the configuration file through the following path: `~/.config/neofetch/config.conf`. Use your favorite text editor to open the file and go to the line of code in the "Backend Settings" section that looks like this:

```bash
image_source="/home/your_user/.config/neofetch/idk.txt"
```

Replace "your_user" with your username and save the changes.

This configuration ensures that Neofetch gets the image from the correct location.

All set! Now you should have Neofetch installed and customized according to your preferences.

---
Remember, this is an initial set of configurations, and you can adjust it to your personal preferences. Enjoy your customized dotfiles setup in XFCE!

I hope you find this documentation helpful!
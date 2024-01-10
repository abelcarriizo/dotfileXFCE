# Mi Primer dotfiles

## Previews
![Main Preview](previews/main_preview.png)
![Window Preview](previews/window_preview.png)

## Clonar Repositorio
Para clonar este repositorio en tu directorio home, utiliza el siguiente comando:

```bash
git clone https://github.com/abelcarriizo/dotfileXFCE.git ~/dotfiles
```

## Instalación Inicial

```bash
sudo apt install mughshot xfce4-terminal
```

Establecer la terminal xfce4-terminal como predeterminada: Configuración -> Aplicaciones Predeterminadas.

```bash
sudo apt install qt5-style-kvantum qt5-style-kvantum-themes
```

### Importante: Estructura de Carpetas

La estructura de carpetas en el repositorio refleja la estructura que se espera en tu directorio home. Debes copiar o cortar el contenido del repositorio y pegarlo directamente en tu directorio home (`/home/tu_usuario`).

### Cambiar Tema, Iconos, Fuentes, etc.

Accede a la aplicación de Configuración y realiza los siguientes pasos:

#### Tema
1. **Apariencia -> Estilo:** Everblush_GTK_THEME

#### Iconos
2. **Apariencia -> Iconos:** Zafiro-icons-Dark

#### Fuente
3. **Apariencias -> Letra:**
   - Tipografía predeterminada: Iosevka Nerd Font Regular, tamaño 10
   - Tipografía monoespaciada predeterminada: JetbrainsMono Nerd Font Mono Regular, tamaño 10

#### Gestor de Ventanas
4. **Gestor de Ventanas:**
   - Tema: Everblush-xfwm
   - Tipografía del título: Iosevka Nerd Font Regular, tamaño 9
   - Alineación del título: Izquierda

#### Ratón y Panel Táctil
5. **Ratón y Panel Táctil:**
   - Tema: Radioactive-nord

#### Kvantum Manager
6. **Kvantum Manager:**
   - Cambiar/Borrar tema: Seleccionar tema Everblush

**Cerrar sesión para aplicar los cambios.**

### Configuración LightDM

1. Accede al directorio `~/.themes` y ejecuta:

```bash
sudo cp -R Everblush /usr/share/themes
```

2. Accede al siguiente directorio y ejecuta:

```bash
sudo cp -R Zafiro-Icons-* /usr/share/icons/
sudo cp -R Papirus* /usr/share/icons/
```

3. Abre la aplicación "Configuración de la interfaz GTK+ de LightDM" desde el menú y selecciona:
   - Tema: Everblush
   - Iconos: Papirus-Dark 
   - Tipo de Letra: Noto Sans Regular 10
   - Fondo de Pantalla:
      - Color: #232a2d

**Cerrar sesión para ver los cambios.**

### Instalación Picom

#### Dependencias

```bash
sudo apt install libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-randr0-dev libxcb-composite0-dev libxcb-image0-dev libxcb-present-dev libxcb-xinerama0-dev libxcb-glx0-dev libpixman-1-dev libdbus-1-dev libconfig-dev libgl1-mesa-dev libpcre2-dev libpcre3-dev libevdev-dev uthash-dev libev-dev libx11-xcb-dev meson libxcb-util1 libxcb-util-dev libxcb-dpms0 libxcb-dpms0-dev
```

Clona el repositorio Picom en el directorio preferido (ej. `~/Descargas`):

```bash
git clone https://github.com/yshui/picom
```

Ejecuta los siguientes comandos para compilar e instalar:

```bash
cd ~/Descargas/picom
git submodule update --init --recursive
meson --buildtype=release . build
ninja -C build
ninja -C build install
```

Desactiva el compositor actual en "Configuración" -> "Ajustes del Gestor de Ventanas" -> "Compositor" y desactiva "Activar composición de visualización".

#### Iniciar Picom

Añade Picom al inicio del sistema:
   - Nombre: Picom Startup
   - Descripción: Picom Compositor
   - Orden: picom
   - Desencadenar: al iniciar sesión

Cerrar sesión para ver los cambios.

### Instalar y Personalizar Neofetch
Continuemos con la última parte:

Para instalar Neofetch, utiliza el siguiente comando:

```bash
sudo apt install neofetch
```

Ahora, personalicemos la configuración de Neofetch. Accede al archivo de configuración a través de la siguiente ruta: `~/.config/neofetch/config.conf`. Utiliza tu editor de texto favorito para abrir el archivo y dirígete a la línea de código en la sección "Backend Settings" que se ve así:

```bash
image_source="/home/tu_usuario/.config/neofetch/idk.txt"
```

Reemplaza "tu_usuario" con el nombre de tu usuario y guarda los cambios.

Esta configuración asegura que Neofetch obtenga la imagen desde la ubicación correcta.

¡Listo! Ahora deberías tener Neofetch instalado y personalizado según tus preferencias.

---
Recuerda que este es un conjunto inicial de configuraciones y puedes ajustarlo según tus preferencias personales. ¡Disfruta de tu configuración personalizada de dotfiles en XFCE!

¡Espero que encuentres útil esta documentación!
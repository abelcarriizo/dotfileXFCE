# My first dotfileXFCE

## Previews
![Main Preview](previews/main_preview.png)
![Main Preview](previews/window_preview.png)

IMPORTANTE
Clonar este repositorio en el tu directorio dentro de home, es decir, /home/<tu_usuario>
git clone https://github.com/abelcarriizo/dotfileXFCE.git

# Instalacion inicial:
sudo apt install mughshot xfce4-terminal

Establecer la terminal de xfce4-terminal como predeterminada ingresando en la aplicacion: Configuracion -> Aplicaciones Predeterminadas.

# Instalar kvantum theme 
sudo apt install qt5-style-kvantum qt5-style-kvantum-themes

# Cambiar tema, iconos, fuentes...
Luego de haber realizado los pasos anteriores accederas a la aplicacion de Configuracion y realizaras lo siguiente:

Tema
1. Acceder a "Apariencia" y seleccionar: 
"Estilo": "Everblush_GTK_THEME"

Iconos
2. Acceder a "Apariencia" y seleccionar: 
"Iconos": "Zafiro-icons-Dark"

Fuente
3. Acceder a "Apariencias" y seleccionar:
"Letra": 
- "Tipografia predeterminada": Iosevka Nerd Font Regular, tamaño 10
- "Tipografia monoespaciada predeterminada": JetbrainsMono Nerd Font Mono Regular, tamaño 10

Gestor de Ventanas
4. Acceder a "Gestor de Ventanas" y luego seleccionar:
"Tema": Everblush-xfwm
"Tipografia del titulo": Iosevka Nerd Font Regular, tamaño 9
"Alineacion del titulo": izquierda

Raton y Panel Tactil
5. Acceder a "Raton y Panel Tactil" y luego seleccionar:
"Tema": Radioactive-nord

Kvantum Manager
6. Acceder a "Kvantum Manager" y luego seleccionar:
"Cambiar/Borrar tema": 
- "Seleccionar tema" Everblush

En este punto puedes cerrar sesion para chequear los cambios 

# Configuracion LightDM 
1. Acceder al siguiente directorio "~/.themes" y luego aplicar los siguientes comandos:
sudo cp -R Everblush /usr/share/themes

2. Acceder al siguiente directorio y luego aplicar los siguientes comandos:
sudo cp -R Zafiro-Icons-* /usr/share/icons/
sudo cp -R Papirus* /usr/share/icons/

3. Acceder a la aplicacion "Configuracion de la interfaz GTK+ de LightDM" desde el menu y luego seleccionar:
"Tema": Everblush
"Iconos": Papirus-Dark 
"Tipo de Letra": Noto Sans Regular 10
"Fondo de Pantalla":
- "Color": #232a2d

Ahora Cerrar Sesion para ver los cambios.

# Instalacion Picom

Dependencias:
sudo apt install libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-randr0-dev libxcb-composite0-dev libxcb-image0-dev libxcb-present-dev libxcb-xinerama0-dev libxcb-glx0-dev libpixman-1-dev libdbus-1-dev libconfig-dev libgl1-mesa-dev libpcre2-dev libpcre3-dev libevdev-dev uthash-dev libev-dev libx11-xcb-dev meson libxcb-util1 libxcb-util-dev libxcb-dpms0 libxcb-dpms0-dev

Clonar el siguiente repositorio (preferentemente en el directorio ~/Descargas):
git clone https://github.com/yshui/picom

Luego utilizar los siguientes comandos:
- git submodule update --init --recursive
- meson --buildtype=release . build
- ninja -C build
- ninja -C build install

Desactivar compositor actual siguiendo estos pasos:
Acceder a la aplicacion "Configuracion" - "Ajustes del Gestor de Ventas" - "Compositor" y luego desactivar
la opcion "Activar composicion de visualizacion"

Iniciar Picom
Para hacer que nuestro nuevo compositor inicie junto con el sistema es importante realizar los siguientes pasos:
Acceder a la aplicacion: "Sesion e Inicio" - "Autoarranque de aplicaciones"y seleccionar "+" para añadir picom. A continuacion se describe que colocar en cada seccion:
"Nombre": Picom Startup
"Descripcion": Picom Compositor
"Orden": picom
"Desencadenar": on login

Ahora Cerrar Sesion para ver los cambios.

# Instalar y Personalizar Neofetch
Para instalar neofetch debes utilizar el siguiente comando:
sudo apt install neofetch

Ahora vamos a configurarlo. Accederemos al archivo de configuracion a traves del siguiente directorio: "~/.config/neofetch/config.conf". Ahora accedemos al archivo desde el editor que tu elijas y nos direccionaremos a la linea de codigo que se encuentra en la seccion de "Backend Settings" que es esta:

image_source="/home/"usuario"/.config/neofetch/idk.txt"

Reemplazaremos "usuario" por el nombre de tu usuario y luego guardaremos y cerraremos el archivo.
![vineyard leaf](images/alpha.svg)

# Imagen Adán

## Tabla de contenidos

- [Introducción](#introducción)
- [Actualización](#actualización)
- [Procedimiento de instalación](#instalación-desde-cero)
- [Instalación de contenidos](#instalación-de-contenidos)
    - [Formato y label de tarjeta externa](#formato-y-label-de-tarjeta-externa)
    - [ROMs](#roms)
    - [Ports](#ports)
    - [Previews](#previews)
    - [BIOS](#bios)
    - [Trucos](#trucos)
    - [Acceso al sistema](#acceso-al-sistema)
- [Controles](#controles)
- [Solución de problemas](#solución-de-problemas)
- [FAQ](#faq)
- [Canal Telegram para comunicar actualizaciones](#canal-telegram-para-comunicar-actualizaciones)

## Introducción

Adán es una imagen para la ranura de tarjeta microSD interna de una serie de consolas portátiles de emulación basadas en chip Ingenic JZ4770. Concretamente las que se mencionan en la descripción de [este commit](https://github.com/OpenDingux/linux/commit/8fdd85c7198ab553dcbb36d3d62441fc9b655ed3), es decir RG350, RG280, RG300X y PlayGo/PocketGo2 v2.

La imagen es un volcado tras realizar una instalación de los siguientes paquetes:

* [OpenDingux](http://od.abstraction.se/opendingux/latest/). Gracias principalmente a [@pcercuei](https://github.com/pcercuei).
* [SimpleMenu](https://github.com/fgl82/simplemenu/releases/tag/10.3). Gracias a [@FGL82](https://github.com/fgl82). Con los siguientes themes:
    * [0A](https://github.com/fgl82/0A). Gracias a [@FGL82](https://github.com/fgl82).
    * [BetaMax](https://github.com/Yarkiebrown/BetaMax-SimpleMenu-theme). Gracias a [@Yarkiebrown](https://github.com/Yarkiebrown).
    * [BigCody](https://github.com/fgl82/BigCody). Gracias a [@FGL82](https://github.com/fgl82).
    * [ComicBook320x240](https://github.com/retrogamecorps/ComicBook320x240) y [ComicBook](https://github.com/retrogamecorps/ComicBook). Gracias a [@retrogamecorps](https://github.com/retrogamecorps).
    * [SimUI](https://github.com/dkodr/SimUI). Gracias a [@dkodr](https://github.com/dkodr).
* [RetroArch](https://www.retroarch.com/?page=platforms). La combinación de Wrappers OPK se ha generado con el script [RG3550_auto_ra_installer](https://github.com/eduardofilo/RG350_auto_ra_installer) en base a [este fichero](https://github.com/eduardofilo/RG350_auto_ra_installer/blob/master/all.csv).
    * [Oficial](https://buildbot.libretro.com/nightly/dingux/mips32/). Gracias principalmente a [@jdgleaver](https://github.com/jdgleaver).
    * [Poligraf](https://github.com/Poligraf/opendingux_ra_cores_unofficial). Gracias a [@Poligraf](https://github.com/Poligraf).
* Aplicaciones standalone:
    * [ColecoD](https://boards.dingoonity.org/gcw-releases/colecod-v1-0/). Gracias a [@alekmaul](https://github.com/alekmaul).
    * [Daphne](https://github.com/DavidKnight247/Daphne). Gracias a [@DavidKnight247](https://github.com/DavidKnight247).
    * [FBA](https://github.com/plrguez/fba-sdl/releases/tag/r19_2021-10-18-.44_od_beta-fix-06). Gracias a [@plrguez](https://github.com/plrguez).
    * [JzIntv](https://github.com/eduardofilo/jzIntv/releases). Gracias a [@DavidKnight247](https://github.com/DavidKnight247).
    * [PCSX4All](https://github.com/jdgleaver/RG350_pcsx4all/releases/tag/1.5). Gracias a [@jdgleaver](https://github.com/jdgleaver).
    * [PocketSNES](https://github.com/m45t3r/PocketSNES/releases/latest). Gracias a [@m45t3r](https://github.com/m45t3r).
    * [ReGBA](https://github.com/jdgleaver/ReGBA/releases/latest). Gracias a [@jdgleaver](https://github.com/jdgleaver).
    * [Tac08](https://0xcafed00d.itch.io/tac08-rg350). Gracias a [@0xCAFED00D](https://itch.io/profile/0xcafed00d).
    * [VbEmu](https://gitlab.com/gameblabla/gameblabla-releases/-/blob/master/opk/gcw0/vbemu_gcw0.opk). Gracias a [@gameblabla](https://gitlab.com/gameblabla).
    * [xMAME](http://www.slaanesh.net/). Gracias a [@Slaanesh](https://www.blogger.com/profile/15791750842821351775). Instalado [este](https://github.com/eduardofilo/RG350_xmame_sm_bridge) interfaz de ajustes.
    * [BeebEm](https://github.com/plrguez/beebem-od). Gracias a [@plrguez](https://github.com/plrguez).
    * [ScummVM](https://downloads.scummvm.org/frs/scummvm/). Gracias principalmente a [@citral23](https://github.com/citral23).
    * [Commander](https://github.com/od-contrib/commander/releases/latest). Gracias a [@glebm](https://github.com/glebm).
    * [uae4all](https://github.com/goldmojo/uae4all/releases/tag/Release-1-params-20201111-r2). Gracias a [@goldmojo](https://github.com/goldmojo).
    * [GMU](https://github.com/plrguez/gmu-odbeta/releases/tag/v0.10.2-rc1-odbeta-20211024). Gracias a [@plrguez](https://github.com/plrguez).
    * [PyBackup](https://github.com/eduardofilo/RG350_py_backup/releases/latest)

Resultado de un proyecto de colaboración del Team RParadise formado por:

* [Brumagix Gamer](https://www.youtube.com/channel/UCrdNisYjDd7qI1Zv2ZLwBrQ)
* [eduardófilo](https://apuntes.eduardofilo.es/)
* Juanmote (Juanma)
* [La Retro Cueva](https://www.youtube.com/channel/UCQm1VwD4sFoOUx6rq-at7jA)

## Actualización

Si se ha estado utilizando la consola con la versión anterior de la imagen, seguramente nos interese guardar los savestates de las partidas que hayamos jugado y algunos ajustes personales. Así pues, **ANTES** de flashear la última versión de la imagen, conviene hacer backup de algunas de estas cosas. Para facilitar esta tarea se puede utilizar la aplicación `Py Backup` que se describe [aquí](https://github.com/eduardofilo/RG350_py_backup/blob/master/README_es.md) y que viene preconfigurada con los archivos más importantes de los que conviene hacer backup periódicamente.

En el siguiente vídeo se muestra el proceso completo de actualización. **IMPORTANTE**: Los pasos 1 al 6 del vídeo sólo serán necesarios en el caso de que la release que vayamos a instalar incorpore entre sus ficheros una configuración para Py Backup mejorada (`config.ini`).

[![Ver vídeo](https://img.youtube.com/vi/Qih9NzvCCHg/hqdefault.jpg)](https://www.youtube.com/watch?v=Qih9NzvCCHg "Ver vídeo")

**CONSEJO IMPORTANTE**: Es áltamente recomendable no flashear directamente sobre la misma tarjeta donde tuviéramos la instalación anterior. Haciéndolo sobre una tarjeta distinta y conservándola durante un tiempo, siempre podremos recuperar algún fichero que echemos en falta (como algún savestate).

**AVISO IMPORTANTE**: Por cambios en el formato interno de los ficheros almacenados en `rom_preferences` y `favorites.sav` en la versión 11 de SimpleMenu instalada a partir de la imagen 1.3, no se deben restaurar las copias de seguridad de estos ficheros procedentes de una versión anterior. Los `rom_preferences` en realidad no hay cambiado el formato interno de los ficheros sino su ubicación. Antes estaban todos en la raíz de ese mismo directorio y ahora van en subdirectorios con el nombre del sistema correspondiente. Por tanto, con un poco de atención, podría aprovecharse un backup de estos ficheros, pero habría que hacer la restauración manualmente o mover los ficheros a los directorios donde ahora SimpleMenu va a buscarlos.

## Instalación desde cero

1. Descargar la imagen del apartado [releases de este repositorio](https://github.com/eduardofilo/RG350_adam_image/releases/latest).
2. Sin necesidad de descomprimir, flashear el archivo (`img.xz`) con [Balena Etcher](https://www.balena.io/etcher/) sobre una tarjeta microSD de al menos 4GB.
3. Montar la microSD en un ordenador. Si la acabamos de flashear, dependiendo del sistema operativo, puede ser necesario extraerla del lector y volverla a insertar. En Windows se montará una de las dos particiones que contiene la tarjeta y la otra dará error. El error es normal dado que la segunda partición es de tipo Linux.
4. Colocar el kernel adecuado al modelo de nuestra consola. Esto puede hacerse de varias maneras en función del sistema operativo del PC.

#### Windows

1. Abrir el script `select_kernel.bat` que hay en la partición que se monta correctamente, haciendo doble clic sobre él.

    ![Win selector script](images/win_selector_script.png)

2. Aparecerá una consola donde tendremos que teclear el número correspondiente a nuestro modelo de consola del listado que veremos.

    ![Win selector script 2](images/win_selector_script2.png)

3. Pulsar Retorno y, cuando se nos indique, expulsar la tarjeta con seguridad.

    ![Win selector script 3](images/win_selector_script3.png)

#### Linux

1. Abrir un terminal y cambiar el directorio actual a la ruta correspondiente a la partición 1 de la tarjeta (podemos averiguar el punto de montaje en nuestro sistema con el comando `df`). Desde ese directorio ejecutar el comando `bash select_kernel.sh`.

    ![Linux selector script](images/linux_selector_script.png)

2. Aparecerá un diálogo que nos invitará a seleccionar nuestro modelo de consola con las teclas de cursor.

    ![Linux selector script 2](images/linux_selector_script2.png)

3. Pulsar Retorno y, cuando se nos indique, expulsar la tarjeta con seguridad.

    ![Linux selector script 3](images/linux_selector_script3.png)

#### Cualquier sistema

Hay un tercer método válido para cualquier sistema operativo (Windows, Linux, Mac). Se trata de visualizar con un explorador de archivos la partición 1 de la tarjeta y copiar manualmente los dos ficheros que hay dentro del directorio correspondiente a nuestro modelo de consola a la raíz de esa partición. Al ser una partición FAT32, no debería haber problema para acceder a los ficheros desde cualquier sistema. Hacer clic en la siguiente miniatura para ver un pequeño vídeo.

[![Ver vídeo](https://img.youtube.com/vi/CQSBWOTO2zc/hqdefault.jpg)](https://www.youtube.com/watch?v=CQSBWOTO2zc "Ver vídeo")

Al llegar a este punto, la tarjeta estará lista para funcionar sobre el modelo de consola que hayamos seleccionado en el procedimiento anterior. Si no lo hemos hecho ya, la expulsaremos con seguridad del PC e insertaremos en la ranura de la consola marcada como INT.

El procedimiento anterior se puede repetir para cambiar a otro modelo de consola en cualquier momento. Es decir, la imagen es compatible con los cuatro modelos de consola soportados por lo que una misma tarjeta nos servirá para varias máquinas.

La partición 2 contenida en el fichero de imagen, tiene unos 3,5GB (por eso se puede flashear sin problemas en tarjetas a partir de 4GB de capacidad). En esta versión de la imagen, esta partición no se auto expandirá hasta ocupar el espacio disponible en la tarjeta. Si se quiere hacer (aunque no es necesario dado que los contenidos pesados van en la tarjeta EXT), se puede hacer con las utilidades [DiskGenius](https://www.diskgenius.com/) de Windows o [GParted](https://gparted.org/) de Linux.

En la primera parte de este vídeo del compañero [Brumagix Gamer](https://www.youtube.com/channel/UCrdNisYjDd7qI1Zv2ZLwBrQ) podemos ver el proceso de instalación:

[![Ver vídeo](https://img.youtube.com/vi/NCfoqQ5-Ll8/hqdefault.jpg)](https://www.youtube.com/watch?v=NCfoqQ5-Ll8 "Ver vídeo")

## Instalación de contenidos

La tarjeta que acabamos de preparar está vacía de contenidos. Sólo contiene el sistema OpenDingux, el frontend SimpleMenu, los cores RetroArch y unos pocos emuladores independientes. Toda la configuración se ha hecho con la idea de que los contenidos sean aportados desde la tarjeta que colocaremos en la ranura marcada como EXT.

Antes de continuar, hacer un breve comentario sobre las consideraciones legales de la instalación de dichos contenidos. El asunto es complejo. Si se tiene interés en profundizar, un buen artículo es [este post de Retro Game Corps](https://retrogamecorps.com/2020/08/18/legal-guide-is-downloading-retro-game-files-roms-illegal/) (en inglés). Aunque existen pocos precedentes legales sobre el tema, el problema afecta fundamentalmente a las BIOS y las ROMs. De forma simplificada se suele considerar que podemos manejar las ROMs de los juegos y las BIOS de las máquinas que tengamos en propiedad. En realidad se trata más de una regla basada en el sentido común, ya que como decimos, existen pocas sentencias sobre el tema y desde luego la opinión de los distintos participantes en la industria no es consistente.

### Formato y label de tarjeta externa

Para que todas las rutas preconfiguradas en la imagen funcionen, es necesario que la tarjeta microSD externa tenga formato FAT32 y **NO** tenga definida una etiqueta o label. En caso de tener label habrá que borrarlo.

En Windows podemos hacerlo desde el cuadro de Propiedades de la unidad en que se monta la tarjeta externa. Hacer clic en la siguiente miniatura para ver un pequeño vídeo.

[![Ver vídeo](https://img.youtube.com/vi/3uAMibsOvvk/hqdefault.jpg)](https://www.youtube.com/watch?v=3uAMibsOvvk "Ver vídeo")

En Linux se puede hacer ejecutando el siguiente comando desde un terminal (en el ejemplo se ha usado el dispositivo `/dev/mmcblk0p1`, pero habrá que sustituirlo por el que corresponda en nuestro caso):

```bash
sudo fatlabel /dev/mmcblk0p1 -r
```

Si tienes un Mac, por ahora la mejor opción es la descrita en la [Starter Guide de Retro Game Corps](https://retrogamecorps.com/2021/08/20/rg350-rg280-series-starter-guide/#Setup), aportada por @Asppire y que se transcribe a continuación:

> "Borra" el disco usando la aplicación `Disk Utility` integrada en el sistema, dando formato MS-DOS (FAT) y con cualquier nombre. Luego, en el lado izquierdo de la aplicación `Disk Utility`, debería aparecer la tarjeta SD. Haz click con el botón derecho sobre ella, selecciona `Rename` y ahora borra el nombre y sustitúyelo por un espacio, de manera que el nombre parezca quedar vacío. Una vez montada en OpenDingux, se interpretará como vacío y funcionará adecuadamente.

### ROMs

El frontend SimpleMenu ha sido configurado con una serie de rutas predefinidas donde tratará de localizar las ROMs y previsualizaciones de las mismas. Dichas rutas serán creadas en la tarjeta EXT cada vez que arranque el sistema (si no existen). Este proceso sólo funcionará si como decíamos en el apartado anterior, el formato de la tarjeta es FAT32 y **NO** tiene label. Si no queremos modificar la configuración de SimpleMenu, habrá que atenerse a estas rutas. En la tabla que hay más abajo, se indica en la segunda columna el nombre del directorio que tendrá que existir en la tarjeta externa cuando la montamos en el PC. Por ejemplo en el pantallazo siguiente está señalado el directorio de ROMs del sistema Game Boy, que como vemos se encuentra junto a todos los demás dentro de la carpeta `roms` en la raíz de la tarjeta.

![SDcard paths](images/sdcard_paths.png)

La ruta anterior en el PC se corresponderá con `/media/sdcard/roms` en el sistema de la consola, una vez que la tarjeta se encuentre en la consola y el sistema se haya iniciado. En caso de modificar la configuración de SimpleMenu, o de abrir manualmente los emuladores desde GMenu2X, ésta será el tipo de ruta que usaremos (por ejemplo `/media/sdcard/roms/GB` para Game Boy).

A continuación se muestra la tabla de los sistemas configurados en SimpleMenu con las rutas donde deberemos situar las ROMs y las extensiones que éstas deben tener:

|Sistema|Rutas|Extensiones soportadas|
|:------|:-----------------|:---------------------|
|MAME|roms/ARCADE|zip, 7z|
|Capcom Play System|roms/CPS|zip, 7z|
|Final Burn Alpha|roms/FBA|zip|
|Daphne|roms/DAPHNE|zip|
|Nintendo NES|roms/FC|nes, zip, 7z|
|Nintendo Famicom Disk System|roms/FDS|fds, zip, 7z|
|Nintendo SNES|roms/SFC|smc, sfc, zip, 7z|
|Nintendo Virtual Boy|roms/VB|vb, vboy, bin, zip, 7z|
|SEGA SG-1000|roms/SG1000|zip, sg, 7z|
|SEGA Master System|roms/SMS|zip, sms, 7z|
|SEGA Megadrive|roms/MD|zip, bin, smd, md, mdx, gen, 7z|
|SEGA CD|roms/SEGACD|bin, chd, cue|
|SEGA 32X|roms/32X|zip, 32x, 7z|
|Atari 2600|roms/A2600|bin, a26, zip, 7z|
|Atari 5200|roms/A5200|bin, a52, zip, 7z|
|Atari 7800|roms/A7800|bin, a78, zip, 7z|
|Inteillivision|roms/INTELLI|int|
|ColecoVision|roms/COLECO|col, cv, bin, rom, zip, 7z|
|SNK Neo Geo|roms/NEOGEO|zip, 7z|
|NEC PC Engine|roms/PCE|pce, tg16, cue, zip, 7z|
|NEC PC Engine CD|roms/PCECD|pce, tg16, cue, chd, zip, 7z|
|Sony PlayStation|roms/PS|mdf, zip, pbp, cue, bin, img, ccd, sub, chd|
|Nintendo Game Boy|roms/GB|gb, gz, zip, 7z|
|Nintendo Game Boy Color|roms/GBC|gbc, zip, 7z|
|Nintendo Game Boy Advance|roms/GBA|gba, zip, 7z|
|Nintendo Game&Watch|roms/GW|mgw, zip, 7z|
|SEGA Game Gear|roms/GG|zip, gg, 7z|
|Atari Lynx|roms/LYNX|zip, lnx, 7z|
|SNK Neo Geo Pocket|roms/NGP|ngp, ngc, 7z, zip|
|WonderSwan|roms/WSC|ws, wsc, zip, 7z|
|Pokemon Mini|roms/POKEMINI|min, zip, 7z|
|Watara Supervision|roms/SUPERVISION|sv, bin, 7z, zip|
|Sinclair ZX Spectrum|roms/ZX|tzx, tap, z80, rzx, scl, trd, dsk, zip, 7z|
|Amstrad CPC|roms/AMSTRAD|dsk, sna, tap, cdt, voc, cpr, m3u, zip, 7z|
|Commodore 64|roms/C64|crt, d64, t64, bin, 7z, zip|
|MSX|roms/MSX|rom, ri, mx1, mx2, col, dsk, cas, sg, sc, m3u, zip, 7z|
|Commodore Amiga|roms/AMIGA|adf, adz, dms, fdi, ipf, hdf, hdz, lha, slave, info, cue, ccd, nrg, mds, iso, chd, uae, m3u, zip, 7z, rp9|
|Doom|roms/DOOM/DOOM, roms/DOOM/DOOM2|wad, zip, 7z|
|Quake|roms/QUAKE/id1, roms/QUAKE/hipnotic, roms/QUAKE/rogue, roms/QUAKE/dopa|pak|
|Quake2|roms/QUAKE2/baseq2, roms/QUAKE2/rogue, roms/QUAKE2/xatrix, roms/QUAKE2/zaero|pak|
|MS-DOS|roms/DOSBOX|zip, dosz, exe, com, bat, iso, cue, ins, img, ima, vhd, m3u, m3u8, 7z|
|ScummVM|roms/SCUMMVM|svm|
|Pico8|roms/PICO8|png|
|TIC80|roms/TIC80|tic, 7z, zip|
|BBC Micro|roms/BBCMICRO|ssd, dsd, uef|

A contnuación se indican aclaraciones sobre algunos sistemas.

#### PlayStation

Las ROMs en formato `cue+bin` no funcionan comprimidas en ZIP. En formato `iso` en cambio sí se abren cuando se suministran comprimidas en ZIP.

#### ScummVM

A partir de la versión 1.4, la forma de instalar los juegos para este sistema difiere mucho entre utilizar el core RetroArch o el emulador standalone. Habrá que decantarse desde un principio por uno u otro emulador y proceder como se indica a continuación:

##### RetroArch

Los juegos ScummVM están compuestos de varios ficheros, por lo que habrá que mantenerlos en directorios. La extensión `svm` indicada en la lista anterior corresponde a un fichero vacío que tenga como nombre el ID del juego que extraeremos de [esta lista](https://www.scummvm.org/compatibility/) y que colocaremos en el directorio donde tengamos el resto de los ficheros del juego. Por ejemplo para el juego "The Secret of Monkey Island" necesitaremos los ficheros que podemos consultar en el [wiki de ScummVM](https://wiki.scummvm.org/index.php?title=Category:Supported_Games). En concreto para este juego [vemos](https://wiki.scummvm.org/index.php?title=The_Secret_of_Monkey_Island) que necesitaremos los ficheros `MONKEY.000` y `MONKEY.001` que colocaremos en un directorio de cualquier nombre dentro del directorio configurado en SimpleMenu (`<EXT_SD>/roms/SCUMMVM`). Será en este mismo directorio donde tendremos que colocar el fichero vacío `svm`. Según la lista de compatibilidad de ScummVM, el ID de "The Secret of Monkey Island" es `monkey`, por lo que el fichero que colocaremos dentro del directorio del juego será `monkey.svm`. Por último, si queremos que SimpleMenu muestre el nombre completo del juego, sólo tendremos que incorporar una entrada como la siguiente en el fichero de alias de SimpleMenu (`/home/media/data/local/.simplemenu/alias.txt`):

```
monkey=The Secret of Monkey Island
```

##### Standalone

Este emulador incorpora un sistema de autoinstalación. Para que el sistema funcione tenemos que crear un fichero vacío de nombre `detect.svm` en la raíz del directorio donde tengamos todos los juegos. En Adán ese directorio será `<EXT_SD>/roms/SCUMMVM`. Podemos crear el fichero desde el ordenador por ejemplo. Una vez instalado el fichero, arrancaremos la consola y accederemos al sistema ScummVM en SimpleMenu. En el listado de juegos sólo deberíamos ver el fichero recién creado. Ajustaremos el emulador `scummvm-2.5.1-gcw0.opk` para lanzar ese fichero y lo abriremos. Tras unos segundos volveremos a SimpleMenu donde deberíamos ver correctamente instalados los juegos que teníamos en el directorio de este sistema.

![ScummVM autodetect 1](images/scummvm_autodetect1.png)

![ScummVM autodetect 2](images/scummvm_autodetect2.png)

Este sistema de autoinstalación hace dos cosas:

1. Genera los ficheros `.svm` que actúan como lanzadores de los juegos y lo hace con nombres largos, por lo que no será necesario actualizar el fichero `alias.txt` de SimpleMenu como se comentaba en las instrucciones dadas para el core RetroArch de ScummVM.
2. Genera el fichero `.scummvmrc` en el directorio home de la partición principal del sistema (en la tarjeta interna), por lo que en caso de volver a instalar la imagen hay que acordarse de respaldar este fichero o repetir el sistema de autoinstalación.

Habrá que acordarse de configurar los juegos que habrán aparecido en el listado para ser lanzados desde el emulador standalone al igual que hicimos con el fichero `detect.svm` que por cierto ya podremos borrar puesto que ya no será necesario.

Más detalles sobre este proceso [aquí](https://github.com/plaidman/rg350p/wiki/scummvm-standalone-improvements) gracias a [@plaidman](https://github.com/plaidman).

#### Quake

Los cuatro directorios configurados en este sistema respetan la estructura necesaria para los distintos Expansion Paks que se describen [aquí](https://docs.libretro.com/library/tyrquake/#loading-quake-and-expansion-paks). Los nombres de los ficheros (`pak0.pak`, `pak1.pak`, ...) dentro de los distintos directorios, no se puede cambiar, pero se pueden usar las previews para distinguir unos de otros.

Como los ficheros `pak` no se pueden renombrar, se confunden entre los distintos juegos y aparecen varios por juego cuando sólo hay que lanzar el `pak0.pak`. Se ha utilizado un truco comentado por @neilswann80 en la discussion #177 consistente en crear un link al fichero a lanzar que sí podremos renombrar. Los links tienen extensión `fbl` y es por tanto la extensión configurada en SimpleMenu. Si los directorios de Quake contienen sus correspondientes ficheros `pak`, los links para los 4 juegos soportados se generan automáticamente cuando la consola es arrancada con la tarjeta externa instalada.

#### Quake2

Los cuatro directorios en este sistema se corresponden con el juego principal más los 3 mission packs soportados. Hay que respetar además los nombres finales de los directorios donde se mantienen los ficheros `.pak`. Hay cuatro cores distintos para cada una de las cuatro variantes. Como los nombres de los ficheros que se lanzan son siempre `pak0.pak`, se ha utilizado la misma técnica descrita en Quake (arriba), es decir se generan links `fbl` (si los directorios de Quake2 contienen sus correspondientes ficheros `pak`) para los cuatro juegos soportados y se configura esa extensión en SimpleMenu.

Es necesario ajustar el OPK correspondiente en SimpleMenu o abrir el adecuado en GMenu2X. La correspondencia es como sigue:

|Juego|Core RetroArch|OPK Wrapper|Directorio para paks|
|:----|:-------------|:----------|:-------------------|
|Quake 2|vitaquake2_libretro.so|retroarch_rg350_QUAKE2.opk|baseq2|
|Quake 2 'Ground Zero' mission pack|vitaquake2-rogue_libretro.so|retroarch_rg350_QUAKE2_rogue.opk|rogue|
|Quake 2 'The Reckoning' mission pack|vitaquake2-xatrix_libretro.so|retroarch_rg350_QUAKE2_xatrix.opk|xatrix|
|Quake 2 'Zaero' mission pack|vitaquake2-zaero_libretro.so|retroarch_rg350_QUAKE2_zaero.opk|zaero|

Se ha utilizado la misma técnica descrita en Quake, es decir se generan links `fbl` para los cuatro juegos soportados y se configura esa extensión en SimpleMenu.

#### MAME

En este sistema hay 3 tipos de emuladores distintos, algunos de ellos soportando romsets distintos a su vez. Se indica a continuación la lista de los romsets soportados en cada combinación. Se enlaza al datafile utilizado en cada caso que puede servir para comprobar la compatibilidad de las ROMs:

* RetroArch core MAME2003: [v0.78](https://www.progettosnaps.net/download/?tipo=dat_mame&file=/dats/MAME/MAME_Dats_078.rar)
* RetroArch core MAME2003+: [v0.78](https://www.progettosnaps.net/download/?tipo=dat_mame&file=/dats/MAME/MAME_Dats_078.rar)
* FBA: [0.2.97.44](https://archive.org/download/rg350_arcade/FBN_v0.2.97.44.dat)
* xMAME romset 84: [0.84](http://www.progettosnaps.net/download?tipo=dat_mame&file=/dats/MAME/MAME_Dats_084.rar)
* xMAME romset 69: [0.69](http://www.progettosnaps.net/download?tipo=dat_mame&file=/dats/MAME/MAME_Dats_069.rar)
* xMAME romset 52: [0.37b16](http://www.progettosnaps.net/download?tipo=dat_mame&file=/dats/MAME/MAME_Dats_037-52.rar), también conocido como 0.52

### Ports

Los ports o juegos irán en el directorio `/media/sdcard/apps` que corresponde con el directorio `apps` en la raíz de la tarjeta externa. En ese directorio deberemos incorporar los OPKs que internamente deberán estar asociados a la categoría `games` para que SimpleMenu los muestre en el listado de la sección `Applications` del grupo `Apps & Games`.

En cuanto a la disponibilidad de estos ports o juegos, la mayoría de ellos son software libre. Un buen recopilatorio puede encontrarse en la Discussion #191 gracias al esfuerzo de @neilswann80, @JORGETECH y @Juanmote.

### Previews

Las previews deberán colocarse en un directorio de nombre `.previews` dentro de cada uno de los directorios de ROMs del listado anterior. Por ejemplo las previews de las ROMs de GB deberán situarse en `roms/GB/.previews` siendo esta la ruta desde la raíz de la tarjeta externa cuando la montamos en el PC. Los ficheros de preview tienen que ser PNGs con el mismo nombre del juego (excepto la extensión).

![Previews path 1](images/previews_path1.png)

![Previews path 2](images/previews_path2.png)

Si hemos respetado las rutas indicadas anteriormente, más tarde en SimpleMenu el juego se representará de la siguiente forma:

![Previews path 3](images/previews_path3.png)

### BIOS

Todos los emuladores instalados en la imagen (RetroArch incluido) tienen redirigidas las rutas donde deben estar las BIOS al directorio `bios` en la tarjeta externa. De forma similar al caso de las ROMs, el directorio `bios` en la raíz de la tarjeta externa, se corresponderá con la ruta `/media/sdcard/bios` en el sistema de la consola.

No todos los emuladores necesitan BIOS. Es el caso de las máquinas que no la tenían o cuya función se ha podido emular. A continuación se indica el fichero de BIOS que habrá que localizar así como el lugar donde lo deberemos colocar. Para ayudar a identificar los ficheros correctos, se indica en caso de conocerlo su tamaño en bytes y un hash MD5. Se marcan también los casos en que la BIOS es imprescindible para que funcione el emulador. En caso de indicarse que `NO`, el emulador funcionará, pero se recomienda instalarla de cara a conseguir la mayor compatibilidad de los juegos. Para comprobar los hashes MD5 se recomienda la utilidad multiplataforma [Quickhash](https://www.quickhash-gui.org/).

Los tamaños y hashes indicados son de BIOS que se han comprobado funcionales, pero no necesariamente las únicas posibles. Es decir, en algunas máquinas existen varias versiones de BIOS posibles, normalmente por haber existido varios modelos de las máquinas (siendo el caso de la PlayStation uno de los más típicos), o por haber desarrollado alguien BIOS con capacidades mejoradas (aquí el caso típico es el de Neo Geo y su UNIBIOS).

|Sistema|Ruta|Tamaño|Hash MD5|¿Necesaria?|
|:------|:---|-----:|:-------|:----------|
|Atari 5200|bios/5200.rom|2048|`281f20ea4320404ec820fb7ec0693b38`|Sí|
|Atari 7800|bios/7800 BIOS (U).rom| |`0763f1ffb006ddbe32e52d497ee848ae`|No|
|SEGACD|bios/bios_CD_E.bin|131072|`e66fa1dc5820d254611fdcdba0662372`|Sí|
|SEGACD|bios/bios_CD_J.bin|131072|`278a9397d192149e84e820ac621a8edd`|Sí|
|SEGACD|bios/bios_CD_U.bin|131072|`854b9150240a198070150e4566ae1290`|Sí|
|Intellivision|bios/exec.bin|8192|`62e761035cb657903761800f4437b8af`|Sí|
|Intellivision|bios/grom.bin|2048|`0cd5946c6473e42e8e4c2137785e427f`|Sí|
|PC Engine CD|bios/syscard3.pce|262144|`390815d3d1a184a9e73adc91ba55f2bb`|Sí|
|Commodore Amiga|bios/kick34005.A500|262144|`82a21c1890cae844b3df741f2762d48d`|Sí para Amiga 500 (core RA o uae4all standalone)|
|Commodore Amiga|bios/kick37175.A500|524288|`dc10d7bdd1b6f450773dfb558477c230`|Sí para Amiga 500+|
|Commodore Amiga|bios/kick40063.A600|524288|`e40a5dfb3d017ba8779faba30cbd1c8e`|Sí para Amiga 600|
|Commodore Amiga|bios/kick40068.A1200|524288|`646773759326fbac3b2311fd8c8793ee`|Sí para Amiga 1200|
|Commodore Amiga|bios/kick40060.CD32|524288|`5f8924d013dd57a89cf349f4cdedc6b1`|No|
|Commodore Amiga|bios/kick40060.CD32.ext|524288|`bb72565701b1b6faece07d68ea5da639`|No|
|Atari Lynx|bios/lynxboot.img|512|`fcd403db69f54290b51035d82f835e7b`|Sí|
|Phillips Videopac|bios/o2rom.bin|1024|`562d5ebf9e030a40d6fabfc2f33139fd`|Sí|
|SNK Neo Geo|roms/NEOGEO/neogeo.zip| | |Sí|
|Nintendo GBA|bios/gba_bios.bin|16384|`a860e8c0b6d573d191e4ec7db1b1e4f6`|No, aunque recomendable|
|PlayStation|bios/SCPH1001.BIN|524288|`924e392ed05558ffdb115408c263dccf`|Sí ya que en la configuración de PCSX4All se ha deshabilitado la BIOS HLE|
|Nintendo GB|bios/gb_bios.bin|256|`32fbbd84168d3482956eb3c5051637f5`|No|
|Nintendo GBC|bios/gbc_bios.bin|2304|`dbfce9db9deaa2567f6a84fde55f9680`|No|
|Pokemon Mini|bios/bios.min|4096|`1e4fb124a3a886865acb574f388c803d`|Sí|
|MSX (BlueMSX)|bios/Machines/| | |Sí|
|MSX (fMSX)|bios/MSX.ROM|32768|`364a1a579fe5cb8dba54519bcfcdac0d`|Sí para MSX|
|MSX (fMSX)|bios/MSX2.ROM| |`ec3a01c91f24fbddcbcab0ad301bc9ef`|Sí para MSX2|
|MSX (fMSX)|bios/MSX2EXT.ROM| |`2183c2aff17cf4297bdb496de78c2e8a`|Sí para MSX2|
|MSX (fMSX)|bios/MSX2P.ROM|32768|`847cc025ffae665487940ff2639540e5`|Sí para MSX2+|
|MSX (fMSX)|bios/MSX2PEXT.ROM|16384|`7c8243c71d8f143b2531f01afa6a05dc`|Sí para MSX2+|
|BBC Micro|bios/acorn_dnfs|16384|`5daed103918277e2065dd7e8d23e57a5`|Sí|
|BBC Micro|bios/basic|16384|`2cc67be4624df4dc66617742571a8e3d`|Sí|
|BBC Micro|bios/os12|16384|`0a59a5ba15fe8557b5f7fee32bbd393a`|Sí|
|Famicom Disk System|bios/disksys.rom|8192|`ca30b50f880eb660a320674ed365ef7a`|Sí|
|ColecoVision|bios/colecovision.rom|8192|`2c66f5911e5b42b8ebe113403548eee7`|Sí con core gearcoleco_libretro de RA; No con standalone ColecoD|

### Trucos

RetroArch lleva integrado un sistema de trucos en base a una serie de ficheros que se pueden obtener de [este repositorio](https://github.com/libretro/libretro-database/tree/master/cht). En la imagen, el directorio donde tenemos que colocar los ficheros, se ha redirigido a la tarjeta externa, al igual que con las ROMs y BIOS. En concreto al directorio `cheats` de la raíz de la tarjeta externa.

Vamos a detallar el proceso utilizando como ejemplo el juego `Adventure Island` de Game Boy:

1. Buscaremos el fichero correspondiente en el [repositorio](https://github.com/libretro/libretro-database/tree/master/cht). En concreto para este juego el fichero es [éste](https://github.com/libretro/libretro-database/blob/master/cht/Nintendo%20-%20Game%20Boy/Adventure%20Island%20(USA%2C%20Europe).cht).
2. Lo copiaremos al directorio `cheats` en la raíz de la tarjeta EXT. En realidad lo más lógico es copiar colecciones completas de sistemas manteniendo la estructura de directorios que vemos en el repositorio.
3. Una vez arrancada la consola con la tarjeta EXT en su lugar, abriremos el juego con RetroArch.
4. Accedemos al menú de RetroArch (`Select + X` o `Power`).
5. Seguimos la ruta: `Quick Menu > Cheats > Load Cheat File (Replace)`.
6. Aparecerá un explorador de archivos que mostrará el contenido de la carpeta `cheats` de la tarjeta EXT. Localizamos el fichero correspondiente al juego y lo seleccionamos.

    ![Cheats 1](images/cheats1.png)

7. Volveremos a la pantalla de Cheats donde veremos que la parte inferior se ha cargado con los trucos. Allí podremos ajustar los que deseemos (el ajuste rápido se hace con las teclas izquierda/derecha de la cruceta).
8. Finalmente aplicamos con `Apply Changes`.

    ![Cheats 2](images/cheats2.png)

9. Si queremos que los ajustes de trucos que hemos hecho se apliquen entre distintas sesiones de juego, tendremos que hacer un override para el juego.

Instrucciones obtenidas de [esta guía](https://retrogamecorps.com/2020/12/24/guide-retroarch-on-rg350-and-rg280-devices/#Cheats) de Retro Game Corps.

PCSX4All también soporta un sistema de trucos. Al igual que en RetroArch, el directorio donde tenemos que colocar los ficheros, se ha redirigido a la tarjeta externa. En concreto al directorio `cheats/PlayStation` de la raíz de la tarjeta externa. Hay que tener en cuenta que los trucos para PCSX4All no tienen el mismo formato que los que hay para `Sony - PlayStation` en el repositorio que hemos indicado antes para obtener trucos para RetroArch.

### Acceso al sistema

Una vez que la tarjeta con el sistema (INT) y con los contenidos (EXT) han sido insertadas en sus correspondientes ranuras, y la consola encendida, podemos acceder al sistema por SSH para hacer algunas personalizaciones que requieren este tipo de acceso (como editar los ficheros de configuración de SimpleMenu o Py Backup). Para lograr el acceso por SSH conectaremos la consola con un cable USB tipo C al ordenador utilizando el mismo conector que se utiliza para cargar (es decir el marcado con DC). En el caso de Windows puede ser necesario instalar [drivers](https://github.com/SeongGino/RetroGame350-AppRepo/blob/master/RG350-signed_driver.zip). En caso de problemas instalando estos drivers, ver [este vídeo](https://www.youtube.com/watch?v=Ib5qfYv6ijc).

En el ordenador podemos utilizar cualquier cliente de FTP configurado con el protocolo SFTP o SCP (por ejemplo WinSCP o Filezilla). El acceso a través del protocolo SSH normal puede lograrse desde una simple consola o terminal ya sea en Windows o Linux, tecleando el siguiente comando:

```
ssh od@10.1.1.2
```

El password del usuario `od` es `untoqebboqvboqudrn`. Si se quiere cambiar o desactivar, hay que utilizar la aplicación `Password` (en la sección `settings` de GMenu2X o `apps` de SimpleMenu).

![Network access 1](images/network_access1.png)

Por defecto la imagen está configurada para hacer uso del acceso USB en modo `Ethernet > RNDIS`, aunque a través de la aplicación `USB Mode`, podemos cambiar al modo `Mass Storage` (MTP) o `Ethernet > ECM`.

![Network access 2](images/network_access2.png)
![Network access 3](images/network_access3.png)

## Controles

A continuación se listan algunas combinaciones de teclas o atajos interesantes que pueden utilizarse con el sistema OpenDingux, SimpleMenu, RetroArch y los emuladores standalone.

|Situación|Atajo de teclado|Efecto|
|:--------|:---------------|:-----|
|OpenDingux|Mantener POWER|Apagar el sistema|
|OpenDingux|Power + Start + Select|Reinicio del sistema|
|OpenDingux|Power + Select|Forzar cierre de aplicación actual|
|OpenDingux|Power + UP|Subir volumen sonido|
|OpenDingux|Power + DOWN|Bajar volumen sonido|
|OpenDingux|Power + RIGHT|Subir brillo pantalla|
|OpenDingux|Power + LEFT|Bajar brillo pantalla|
|OpenDingux|Power + A|Modo de relación de aspecto en el escalado por hardware|
|OpenDingux|Power + B|Activa/desactiva el modo ratón (anteriormente POWER + L1)|
|OpenDingux|Power + Y|Suspender sistema (pulsar POWER para despertar)|
|OpenDingux|Power + X|Captura de pantalla (en `~/screenshots`)|
|OpenDingux|A (durante el arranque)|Muestra la salida de los scripts de arranque en lugar del logo de boot|
|OpenDingux|Select (durante el arranque)|Boot mode. Revisar [esta guía](https://boards.dingoonity.org/retrominirs-90/a-quick-guide-to-flashing-opendingux-on-the-rs-90-using-windows-10-x64/msg186557/#msg186557)|
|SimpleMenu|Start|Abre la pantalla de ajustes|
|SimpleMenu|Select|Opciones de ROM. Permite seleccionar autoarranque, emulador (si se han definido varios en el sistema) y overclocking|
|SimpleMenu|Up|Seleccionar juego/sección/grupo anterior|
|SimpleMenu|Down|Seleccionar juego/sección/grupo siguiente|
|SimpleMenu|Left|Salta a la página siguiente de la sección actual|
|SimpleMenu|Right|Salta a la página anterior de la sección actual|
|SimpleMenu|R1|Alterna entre la lista de juegos o el modo pantalla completa|
|SimpleMenu|R2|Refresca la lista de juegos del sisema actual (en caso de haber añadido juegos nuevos con el frontend en ejecución)|
|SimpleMenu|A|Abre el juego o aplicación seleccionado|
|SimpleMenu|B|Vuelve atrás|
|SimpleMenu|X|En los listados de juegos, marca el seleccionado como favorito; en la vista de Favoritos borra el juego de la lista|
|SimpleMenu|Y|Abre la selección de Favoritos|
|SimpleMenu|B + Left|Desplaza el listado de juegos a la letra anterior|
|SimpleMenu|B + Right|Desplaza el listado de juegos a la letra siguiente|
|SimpleMenu|B + Up|Cambia al sistema anterior sin mostrar el logo|
|SimpleMenu|B + Down|Cambia al sistema siguiente sin mostrar el logo|
|SimpleMenu|B + Select|Abre un juego aleatorio del sistema actual|
|SimpleMenu|B + X|Borra el juego actual **SIN PEDIR CONFIRMACIÓN**; no funciona en las secciines Favoritos, Apps o Games|
|SimpleMenu|B + A|Lanza el emulador sin pasar un juego como parámetro, si el emulador soporta ser abierto de manera independiente (por ejemplo con FBA permite abrir la interfaz UX)|
|RetroArch|Select + A|Pausa|
|RetroArch|Select + B|Reset|
|RetroArch|Select + X o Power|Menú RetroArch. En algunos cores (G&W por ejemplo) el atajo `Select + X` colisiona con los atajos propios del core; utilizar `Power` en ese caso|
|RetroArch|Select + Y|Avance rápido|
|RetroArch|Select + R1|Guardar savestate|
|RetroArch|Select + L1|Cargar savestate|
|RetroArch|Select + R2|Cambiar disco|
|RetroArch|Select + L2|Abrir bandeja CD|
|RetroArch|Select + Start|Cerrar juego|
|RetroArch|Select + Left/Right|Cambiar slot savestate|
|RetroArch|Select + Up/Down|Cambiar volumen|
|RetroArch/Neo Geo FBA|Mantener pulsado Start|Entrar en ajustes UniBIOS|
|RetroArch/CPS2|R2 o R3|Test menu en algunos juegos|
|RetroArch/Famicom Disk System|L1|Cambiar cara de disco|
|RetroArch/Famicom Disk System|R1|Insertar/eyectar disco|
|FBA (MAME, FBA y CPS)|L1 + R1 + Start o Power|Abre el menú del emulador que nos permite salir|
|FBA (MAME, FBA y CPS)|L1 + R1 + Y|Mostrar/ocultar el contador FPS|
|FBA (MAME, FBA y CPS)|L1 + R1 + B|Guardar savestate|
|FBA (MAME, FBA y CPS)|L1 + R1 + A|Cargar savestate|
|FBA (MAME, FBA y CPS)|Select|Insertar moneda|
|FBA (MAME, FBA y CPS)|Start|Comenzar Jugador 1|
|FBA (MAME, FBA y CPS)|Select + Start|Comenzar Jugador 2|
|xMAME|Select + L1 + R1|Salir del juego|
|xMAME|Start + R1|Mostrar/ocultar el contador FPS|
|Daphne|L1|Insertar moneda|
|Daphne|Start|Comenzar juego|
|Daphne|Select|Salir del juego|
|PocketSNES (SNES)|Select + Start o Power|Abre el menú del emulador que nos permite salir|
|ReGBA (GBA)|Select + Start o Power|Abre el menú del emulador que nos permite salir|
|PCSX4All (PlayStation)|Select + Start o Power|Abre el menú del emulador que nos permite salir|
|JzIntv|Select|Abre el menú del emulador que nos permite salir|
|JzIntv|Power|Cierra el emulador|
|JzIntv|R1|Controlador virtual|
|JzIntv|L1|Teclado virtual|
|ColecoD (ColecoVision)|Select + Start|Abre el menú del emulador que nos permite salir|
|Tac08 (PICO8)|Start|Abre el menú del emulador que nos permite salir|
|Fuse (ZX Spectrum)|Select|Teclado virtual|
|Cap32 (AMSTRAD CPC)|Y + Start|Teclado virtual. Una vez desplegado abrir/cerrar el menú de RA (Select + X) para que empiece a funcionar el stick izquierdo como ratón|
|Vice 64 (Commodore 64)|Select|Teclado virtual|
|PUAE (Commodores Amiga)|L1|Teclado virtual|
|BeebEm (BBC Micro)|L1|Abre el menú del emulador que nos permite salir|
|BeebEm (BBC Micro)|R1|Teclado virtual|

No te pierdas [esta cheatsheet](https://github.com/eduardofilo/RG350_adam_image/blob/39374ad5ea51dd60627358626dd1531e352e0b59/resources/Adam%20Image%20Cheatsheet%20v1.3.pdf) elaborada por @iammeat que incluye todos los controles anteriores en un formato mucho más conveniente.

## Solución de problemas

#### Unsupported video mode

Algunos cores de RetroArch muestran la siguiente pantalla de error al trabajar en resoluciones no soportadas por el sistema:

![Unsupported video mode 1](images/unsupported_video1.png)

Estos casos se suelen solucionar activando algún filtro y jugando con las opciones de scaling de vídeo. Uno de los filtros que suele dar buen resultado es: `Upscale_256x-320x240`. El procedimiento completo para realizar estos cambios sería:

1. Abrir menú RetroArch (`Select + X`).
2. Ir a `Main Menu > Settings > Video > Scaling` y marcar las opciones `Integer Scale` y `Keep Aspect Ratio`.

    ![Unsupported video mode 2](images/unsupported_video2.png)

3. Ir a `Main Menu > Settings > Video > Video Filter` y seleccionar el filtro `Upscale_256x-320x240.filt` (el último de la lista):

    ![Unsupported video mode 3](images/unsupported_video3.png)

Por último, si no se quiere hacer este cambio cada vez que se abra el juego, ir a `Main Menu > Quick Menu > Overrides` y seleccionar `Save Game Overrides`.

Otro filtro que suele dar buen resultado en estas situaciones es `LQ2x`.

#### Forzar cierre de aplicaciones

Si en alguna ocasión la aplicación o emulador que tuviéramos en ejecución se quedara congelada, se puede forzar su cierre pulsando la combinación de teclas `Power + Select`. Es importante pulsar las teclas en ese orden, es decir, pulsar un poco antes `Power` y sin soltarlo pulsar entonces `Select`. Si esta combinación de teclas tampoco funcionara, mantener la tecla `Power` unos segundos para provocar un apagado controlado de la consola.

En resumen, los métodos para forzar el cierre de las aplicaciones o emuladores son:

1. Primero intentar el cierre normal (`Power + Select` por ejemplo en RetroArch).
2. Si lo anterior no funciona, `Power + Select`.
3. Si lo anterior no funciona, mantener `Power` unos segundos hasta que el sistema se apague.

Hay que evitar pulsar `Reset` ya que se ha encontrado con bastante frecuencia que provoca la corrupción de la SD.

#### Riesgo haciendo Overclocking

Otra situación que conduce a la corrupción de la SD en algunos usuarios es el uso del overcloking. Así pues siempre que se vaya a intentar, se recomienda hacer un backup de los savestates y configuraciones que no queramos perder con [Py Backup](https://github.com/eduardofilo/RG350_py_backup/blob/master/README_es.md).

#### Ajuste de emulador preferido

En la configuración hecha de SimpleMenu, muchos de los sistemas ofrecen varias opciones de emulación, es decir se puede elegir entre varios emuladores o cores RetroArch. Además el ajuste del emulador o core RA preferido se puede guardar para cada juego.

En los sistemas sencillos de emular, como las máquinas de 8 bit, sólo se ha ofrecido RetroArch, por considerarlo la mejor opción. Pero en sistemas más complejos, como los sistemas arcade, la oferta de emuladores es amplia. Por ejemplo en MAME se dispone de las siguientes opciones:

* Core RetroArch MAME2003
* Core RetroArch MAME2003+
* FBA
* xMAME romset 84
* xMAME romset 69
* xMAME romset 52

Las opciones de emulación aparecen en este orden en el listado, tratándose la primera como opción predeterminada en caso de no indicar manualmente un emulador para un juego concreto. Por tanto, si no se cambia, la opción predeterminada para ejecutar los juegos del sistema MAME será el core MAME2003 de RetroArch.

Si un juego en concreto no funciona con el emulador predeterminado, pulsaremos `Select` en el listado de juegos de SimpleMenu. Aparecerá un selector con tres opciones, siendo la del emulador a utilizar la tercera. Nos desplazaremos hasta esta tercera opción y cambiaremos el emulador pulsando izquierda/derecha en la cruceta. Para guardar el cambio pulsaremos `Select` de nuevo. Al abrir el juego pulsando `A` se lanzará el core que hayamos elegido. Si el nuevo emulador tampoco funciona correctamente, probar con otra opción hasta obtener un rendimiento adecuado.

![Core selection](images/core_selection.gif)

Otra situación en las que nos conviene cambiar es cuando el juego se ejecuta lento. Además del sonido entrecortado, la mejor forma de medir si el juego se mueve con soltura es activar el contador de frames por segundo o FPS. En RetroArch podemos activar la opción para un juego en particular en el menú `Main Menu > Settings > On-Screen Display > On-Screen Notifications > Notification Visibility > Display Framerate`, pero si queremos activarlo en general, antes hay que cerrar el contenido que estemos ejecutando. Este sería el procedimiento descrito en detalle.

1. Lanzamos un juego que se ejecute con RetroArch (por ejemplo todos los sistemas tipo Handheld están configurados con RetroArch por defecto).
2. Abrimos el menú de RetroArch pulsando `Select + X`.
3. Seleccionar el menú `Close Content`.
4. Seguir el siguiente camino en los menús: `Main Menu > Settings > On-Screen Display > On-Screen Notifications > Notification Visibility`.
5. Activar la opción `Display Framerate`.
6. Volver hasta el menú raíz pulsando `B` repetidas veces.
7. Entrar en el menú `Configuration File`.
8. Ejecutar el comando de menú `Save Current Configuration`.
9. Volver hasta el menú raíz pulsando `B` una vez.
10. Ejecutar el comando de menú `Quit RetroArch`.

Para desactivarlo procederemos de la misma forma pero desactivando la opción del paso 5.

En xMAME la opción FPS se activa/desactiva en cualquier momento pulsando `Start + R1`. En FBA la combinación es `L1 + R1 + Y`.

Un caso especial es el del sistema CPS. En esta imagen se ha optado por juntar en un mismo sistema los CPS1 y CPS2 (no hay core de RetroArch para CPS3 y en general es un sistema para el que las máquinas que pueden utilizar esta imagen no tienen potencia suficiente). Se ha preferido hacerlo así por el reducido número de juegos de ambos sistemas y por las facilidades que ofrece SimpleMenu para seleccionar el core que queremos utilizar para cada juego. Así, en este sistema (o mejor dicho en la reunión de los dos sistemas CPS1 y CPS2), será imprescindible hacer el ajuste en los juegos de CPS2. El core de CPS1 es el predeterminado y por eso sólo será necesario ajustar los de CPS2. La lista completa de juegos CPS2 es la siguiente (se indica el nombre del fichero de la ROM .zip, no el nombre real del juego). Gracias a @ridsama por elaborar la lista:

```
1944, 19xx, armwar, avsp, batcir, choko, csclub, cybots, ddsom, ddtod, dimahoo, dstlk, ecofghtr, gigawing, hsf2, megaman2, mmatrix, mpang, mshvsf, msh, mvsc, nwarr, progear, pzloop2, ringdest, sfa2, sfa3, sfa, sfz2al, sgemf, spf2t, ssf2t, ssf2, vhunt2, vsav2, vsav, xmcota, xmvsf
```

#### La consola no arranca tras flashear

Lo más probable será que no se ha realizado el procedimiento de instalación del kernel descrito [aquí](#instalación-desde-cero). Si se arranca la consola sin haber instalado el kernel, el LED verde de encendido se ilumina débilmente. En esa situación la consola no se puede apagar (a no ser que desconectemos la batería o esperemos a que se descargue completamente). Se ha comprobado que en algunas tarjetas, aunque extraigamos la tarjeta, instalemos el kernel, volvamos a insertarla y pulsemos el RESET, seguirá sin arrancar. En esas situaciones, la única forma que se ha encontrado para salir del callejón sin salida (aparte de la idea comentada antes de desconectar la batería o esperar a que se descargue completamente) es insertar otra tarjeta que no dé este problema, pulsar RESET y tras el arranque del sistema en esta tarjeta de apoyo, apagar normalmente. Si ahora insertamos la primera tarjeta recien flasheada donde se haya realizado el procedimiento de instalación del kernel, esta vez (con un encendido en frío de la máquina) arrancará normalmente.

#### La consola no se puede apagar

Nos referimos a la situación en que tratamos de apagar la consola mediante el lanzador `Power off` de GMenu2X o el comando `Shutdown` de SimpleMenu. Cuando sucede el problema, justo cuando la consola debería quedar apagada, inicia un nuevo arranque, resultando imposible apagarla completamente. Hasta ahora se han encontrado dos situaciones que pueden producir este problema (aparte del caso de la PG2v1 que tiene su propio escenario). Un caso es tras un reinicio espontáneo del sistema tras entrar y salir varias veces sucesivas del modo de suspensión. El otro es tras haber utilizado la salida HDMI y haberla desconectado (ver discussion #131). La solución consiste en utilizar el Reset. Para evitar corrupciones de la tarjeta del sistema, se recomienda pulsar el Reset justo cuando el sistema acabe de cerrarse (podemos guiarnos por cuando la pantalla se pone en negro). En el siguiente vídeo puede verse un ejemplo del fenómeno y su solución:

[![Ver vídeo](https://img.youtube.com/vi/hf4fGnCjfTw/hqdefault.jpg)](https://www.youtube.com/watch?v=hf4fGnCjfTw "Ver vídeo")

#### La consola no se puede apagar (PG2v1)

Este es un caso especial del anterior. Sólo ocurre con las consolas PlayGo/PocketGo2 v1. En este caso el desencadenante es la desconexión o descarga completa de la batería. El usuario @esmith13 en el ámbito de la issue #7 describe la solución como sigue:

>Descarga el firmware stock para la PG2v1 desde aquí: https://github.com/retrogamehandheld/PocketGo2/wiki/Firmware-and-software-updates
>
>Grábalo a una tarjeta mSD vacía y arranca una vez la consola con ella, luego apaga normalmente (quedará apagada como debería ser).
>
>Cambia a la tarjeta mSD con la imagen ADAM y a partir de entonces todo volverá a la normalidad.
>
>Debería ir bien mientras no reflashees de nuevo tu tarjeta mSD con la imagen ADAM, desconectes la batería, o permitas que se descargue completamente. Si algo de esto ocurre, vuelve a arrancar una vez desde la imagen stock para solucionar el problema otra vez.
>
>Enjuagar y repetir.

#### Bucle de reinicios tras arrancar

En realidad en esta situación que vamos a describir el sistema está completamente arrancado y funcionando. El problema suele estar relacionado con SimpleMenu cuando es el lanzador predeterminado si tiene problemas para restaurar el estado previo. Esto puede ocurrir si se ha modificado manualmente los ficheros que SimpleMenu direcciona a través de sus ficheros de configuración. También puede suceder si se han modificado dichos ficheros (los que se encuentran en `/media/data/local/home/.simplemenu/section_groups`). La solución suele ser borrar el fichero de estado para que se regenere. Dicho fichero es `last_state.sav` y se encuentra dentro del directorio home de SimpleMenu, es decir `/media/data/local/home/.simplemenu`.

Desde la versión 1.3.1 de la imagen, hay una forma de solucionar el problema desde la misma consola. Los pasos para encontrar la solución son los siguientes:

1. Mantener pulsada la tecla Power durante un par de segundos para apagar el sistema.
2. Encender el sistema mientras se mantiene pulsada la tecla `B` durante el arranque completo.
3. Abrir Commander.
4. Borrar el fichero `last_state.sav` dentro del directorio `.simplemenu`.
5. Cerrar Commander.
6. Abrir SimpleMenu.
7. Restablecer los ajustes que se habrán perdido.
8. La situación ahora debería ser normal.

En el siguiente vídeo podemos ver todo el proceso:

[![Ver vídeo](https://img.youtube.com/vi/iuYlIC36uDg/hqdefault.jpg)](https://www.youtube.com/watch?v=iuYlIC36uDg "Ver vídeo")

## FAQ

#### Q1: ¿Tengo que volver a flashear con cada nueva imagen? ¿No existe un OPK para una actualización más ágil?

Lo siento. Por ahora el flasheo es el único medio disponible. En el pasado, con otra imagen, publiqué un OPK para hacer las actualizaciones, pero hubo muchos problemas con las personalizaciones que los usuarios hacían que afectaba al sistema de aplicación de los parches. El procedimiento completo para actualizar entre una versión de la imagen y la siguiente se describe [aquí](#actualización).

#### Q2: ¿Hay algún indicador del nivel de batería?

Desde la versión v1.1, SimpleMenu muestra el nivel de batería en algunos themes (0A and SimUI). También se muestra un indicador de batería cuando se está ejecutando RetroArch y se entra en el menú (`Power` or `Select + X`). Por último, se puede salir a GMenu2X desde SimpleMenu cambiando la opción `Default launcher` a `no` y seleccionando después `Session: quit`.

#### Q3: ¿Por qué no se conservan los overrides de ajustes en RetroArch?

La clave en este tema es comprender bien los tres niveles de overrides que existen. Si se cambia un ajuste y se hace override a nivel de core, pero luego existe un override del mismo ajuste a novel de contenidos, el primero no se aplicará porque el segundo tiene prioridad. [Esta guía](https://docs.libretro.com/guides/overrides/) es muy útil.

Vamos a mostrar un ejemplo de uno de estos casos que se pregunta más a menudo. Se trata de activar la opción para mantener la relación de aspecto de la pantalla en GB o GBC. Vamos a fijarnos en GBC en concreto por lo que en los greps siguientes no hay que tener en cuenta el fichero `GB.cfg`. Esa opción se llama `video_dingux_ipu_keep_aspect` en los ficheros de configuración de RetroArch. Lo que sigue es la situación de partida de ese ajuste en los diferentes ficheros que se aplica, tal y como está en la imagen recien flasheada:

```
rg280v:~/.retroarch $ grep video_dingux_ipu_keep_aspect retroarch.cfg
video_dingux_ipu_keep_aspect = "true"
rg280v:~/.retroarch $ grep video_dingux_ipu_keep_aspect config/Gambatte/*
config/Gambatte/GB.cfg:video_dingux_ipu_keep_aspect = "false"
config/Gambatte/GBC.cfg:video_dingux_ipu_keep_aspect = "false"
config/Gambatte/Gambatte.cfg:video_dingux_ipu_keep_aspect = "false"
```

En palabras, el ajuste `Keep Aspect Ratio` está activado a un nivel general (primer grep), pero desactivado en los overrides a nivel de core y de contenido (segundo grep).

Lo esperable sería que activando la opción a nivel de contenido empezara a aplicarse, pero RetroArch tiene una especie de economía de ajustes y cuando ve que un ajuste a cualquier nivel, encaja con el ajuste general, simplemente elimina ese ajuste del override. Como resultado, cuando cambiamos ese ajuste a `true` y luego creamos el override a nivel de contenido, lo que ocurre en realidad es que el override se pierde y se empieza a aplicar el que está a nivel de core, que, como puede verse, es todavía `false`.

```
rg280v:~/.retroarch $ grep video_dingux_ipu_keep_aspect retroarch.cfg
video_dingux_ipu_keep_aspect = "true"
rg280v:~/.retroarch $ grep video_dingux_ipu_keep_aspect config/Gambatte/*
config/Gambatte/GB.cfg:video_dingux_ipu_keep_aspect = "false"
config/Gambatte/Gambatte.cfg:video_dingux_ipu_keep_aspect = "false"
```

La solución es hacer otro override a nivel de core (lo que borra el ajuste a ese nivel también), dejando únicamente el ajuste general.

```
rg280v:~/.retroarch $ grep video_dingux_ipu_keep_aspect retroarch.cfg
video_dingux_ipu_keep_aspect = "true"
rg280v:~/.retroarch $ grep video_dingux_ipu_keep_aspect config/Gambatte/*
config/Gambatte/GB.cfg:video_dingux_ipu_keep_aspect = "false"
```

En resumen, hay que activar el mantener la relación de aspecto y crear overrides a nivel de core y de contenido al mismo tiempo. Es un lío sí.

#### Q4: ¿Cómo se puede resetear la configuración de RetroArch de manera que pueda montar mis propios overrides sin que se vean afectados por los que incorpora la imagen?

Sólo hay que borrar el directorio `/media/data/local/home/.retroarch/config` y el fichero `/media/data/local/home/.retroarch/retroarch.cfg`.

#### Q5: Las ROMs de NeoGeo con el emulador FBA standalone no sincronizan bien la pantalla en RG350M (supongo que tampoco en RG3300X). ¿Cómo puede arreglarse?

Se trata de un problema con el hardware scaling que hace ese emulador cuando se tiene esa pantalla. La solución es desactivarlo por medio del interfaz propio de FBA o UX. Para ello, desactivar momentaneamente SimpleMenu como lanzador predeterminado, abrir desde GMenu2X el emulador `FBA UX`, localizar el juego que nos interesa ajustar (puede ser necesario añadir la ruta de las ROMs de NEOGEO a `ROMs Paths`), abrirlo y en el menú de opciones que aparece cambiar `Hardware scaling` a `Off`. El cambio se guarda a nivel de juego por lo que si luego más tarde lo lanzamos desde SimpleMenu, se aplicará aunque no pasemos por esa pantalla intermedia de ajustes.

![FBA Hardware scaling](images/fba_hardware_scaling.png)

Si no se quiere hacer el ajuste juego a juego, puede cambiarse en `Main settings > Default ROM settings > Default Run Game settings > Hardware scaling`, pero hay que tener en cuenta que este cambio afectará a los juegos de otros sistemas que no tenían el problema de Neo Geo.

#### Q6: No puedo modificar la configuración de RetroArch, obtengo el error `Failed saving config to...`

Para modificar la configuración general de RetroArch, no debe haber ningún contenido (ROM) cargado. Esto puede hacerse de varias formas:

1. Tras lanzar RetroArch mediante alguna ROM, abrir el menú de éste (`Power` o `Select + X`) y usar el comando `Close Content`.
2. Abrir el lanzador de RetroArch. En versiones de la imagen 1.2 o anteriores, sólo se puede hacer desde GMenu2X, encontrándose en la sección `emulators`. A partir de 1.3 también hay un lanzador en la sección `Apps` de SimpleMenu.

De todas formas no suele ser habitual manipular la configuración general de RetroArch. Lo que la mayoría de las veces conviene es hacer un override a nivel de core, directorio o juego. Revisar la FAQ número 3 para más detalles.

#### Q7: ¿Cómo puedo bajar el volumen mínimo sin llegar a desactivar el sonido? El mínimo es todavía muy alto.

Este problema afecta principalmente a RG280V. Eso es porque en esta máquina los altavoces están conectados directamente al DAC (convertidor analógico digital) y no a la cadena DAC->puerto de auriculares como en otros dispositivos. En RG280V, el control de volumen solo se ve afectado por el canal PCM en `alsamixer`, e incluso en su valor mínimo antes del mute (32 / -30dB) se escucha demasiado alto en un ambiente silencioso.

![alsamixer](images/alsamixer.png)

Sin tocar el sistema, lo único que se puede hacer es jugar con las opciones de sonido que puedan tener algunos de los emuladores. Afortunadamente RetroArch incluye en los ajustes de audio la posibilidad de atenuar la salida. El ajuste se encuentra en la ruta: `MAIN MENU > Settings > Audio > Volume Gain (dB)`. Se ha encontrado que el valor `-10dB` es un buen equilibrio, de manera que el ajuste del volumen mínimo del sistema antes de mute ya resulta adecuado, y el máximo es suficientemente potente. Si optamos por hacer este ajuste, lo mejor es hacerlo a nivel de la configuración general, para lo que hay que seguir los pasos comentados en la [FAQ número 6](#q6-no-puedo-modificar-la-configuraci%C3%B3n-de-retroarch-obtengo-el-error-failed-saving-config-to).

![RA audio gain](images/ra_audio_gain.png)

#### Q8: ¿Puedo actualizar Adán con las últimas versiones de OpenDingux beta?

Por supuesto. Adam no es más que una instalación normal de los paquetes listados al principio de este documento, es decir, OpenDingux beta, RetroArch, SimpleMenu y unos cuantos emuladores independientes. Ninguno de ellos ha sido modificado, por lo que deberían de tener el funcionamiento esperado. No sólo puedes actualizar los paquetes, sino que te recomendamos que lo hagas, para ayudar al desarrollo de los mismos.

Aunque se recomienda seguir las instrucciones particulares de cada paquete, éstas son las instrucciones generales para actualizar cada tipo:

* OpenDingux beta: Descargar la compilación que se quiere instalar (normalmente la última) desde su [sitio de distribución](http://od.abstraction.se/opendingux/latest/). Copiar el tipo de OPK adecuado a la consola (en caso de Adam, siempre será el tipo `gcw0`) dentro del directorio `apps` de la tarjeta externa. Localizar el lanzador en la sección `applications` de GMenu2X o SimpleMenu (en este landazor, si antes no se ha abierto otra aplicación de tipo terminal como `USB Mode` por ejemplo, no llega a conmutarse correctamente al modo terminal, quedando el logo de OpenDingux en pantalla; si se abre y ocurre esto, pulsar `Power+Select` para forzar el cierre del OPK), abrirlo y seguir las instrucciones en pantalla. **ADVERTENCIA:** Hay que tener en cuenta, que una vez hecho esto, no se podrá utilizar el script para cambiar entre distintos modelos de consola, ya que si se hace se terminará teniendo un rootfs actualizado con un kernel antiguo, ya que el script copia los kernels instalados originalmente en la imagen, desde las copias que hay en los distintos directorios con los nombres de las máquinas que hay en la partición boot.
* RetroArch: El paquete que puede encontrarse en el [sitio de distribución](https://buildbot.libretro.com/nightly/dingux/mips32-odbeta/) contiene las piezas que hay que instalar manualmente en la consola (un OPK para lanzar RA a modo frontend y hacer la configuración general, un binario que hay que copiar en `/media/data/local/bin` y el directorio de home que contiene los cores y configuraciones básicas). Alternativamente puede usarse [éste instalador](https://github.com/eduardofilo/RG350_auto_ra_installer) del que se ofrecen en las [releases](https://github.com/eduardofilo/RG350_auto_ra_installer/releases) un paquete diseñado para encajar en Adán.
* SimpleMenu y emuladores independientes: Todas estas aplicaciones funcionan como OPKs normales. Por tanto para actualizarlas, tan sólo hay que localizar la versión que se quiera instalar (por ejemplo las releases de SimpleMenu se obtienen de [aquí](https://github.com/fgl82/simplemenu/releases)) y copiarlas al directorio `/media/data/apps`. También pueden copiarse al directorio `apps` de la tarjeta externa, pero en ese caso si no borramos el equivalente en `/media/data/apps`, nos aparecerán por duplicado en los lanzadores.

#### Q9: ¿Es posible utilizar un adaptador WiFi?

Sí, aunque la lista de chipsets soportados es reducida. De momento los soportados son los siguientes:

* Realtek RTL8192CU
* Mediatek MT7601U

Si en el futuro nuevos chipsets son incorporados al sistema, aparecerán listados en el directorio `/lib/modules/5.15.0-rc6-opendingux/kernel/drivers/net/wireless/`

#### 10: ¿Por qué no aparecen en SimpleMenu las ROMs que acabo de cargar en la tarjeta externa?

Hay varias cosas a tener en cuenta para que las ROMs se visualicen:

1. El formato de la tarjeta externa debe ser FAT32.
2. Las ROMs deben encontrarse en los directorios adecuados para el sistema al que pertenecen y que se encuentran listados en la tabla que hay en la sección [ROMs](#roms).
3. Las extensiones de los ficheros de las ROMs deben ser las que se indican en la tabla que hay en la sección [ROMs](#roms).
4. Para acceder al listado de ROMs del sistema que nos interese ver, hay que utilizar los atajos de navegación entre sistemas y grupos que se indican en la tabla que hay en la sección [Controles](#controles). Básicamente son `B` para subir un nivel, `A` para bajar un nivel y `Arriba/Abajo` para moverse entre los distintos elementos que hay en cada nivel. Por ejemplo en el siguiente vídeo se muestra cómo llegar al listado de ROMs de Game Boy desde la sección `Applications` que aparece de forma predeterminada tras flashear la imagen.

[![Ver vídeo](https://img.youtube.com/vi/0npzNmlPJb0/hqdefault.jpg)](https://www.youtube.com/watch?v=0npzNmlPJb0 "Ver vídeo")

#### 11: ¿Por qué el indicador de batería no muestra los niveles correctos?

La batería es uno de los elementos más analógicos que hay en la consola. No hay dos iguales. Para gestionar esta realidad, los modernos smartphones mantienen mucha información sobre las cargas previas y el ritmo y condiciones en que se produce la descarga. Con toda esa información estiman una capacidad de la batería lo más realista posible. En el sistema de la consola no se mantienen esos datos por lo que la capacidad de la batería se estima directamente a partir del voltaje que ésta ofrece en un determinado momento. Como valores para el voltaje asociado a la carga máxima y mínima se utilizan unos valores fijos (4,2V y 3,4V respectivamente) que pueden no ser adecuados para todas las baterías, de ahí que algunas consolas estimen mal el nivel de carga.

Hay también un sensor en el conector de carga, pero éste sólo determina si hay un cable conectado a la consola, no que la batería se esté cargando, es decir, el otro extremo del cable puede estar desconectado y la mayoría de los programas indicará que la consola está siendo alimentada.

Por último comentar que los indicadores de carga de los distintos programas (GMenu2X, SimpleMenu, RetroArch, RG350 test) pueden estar programados de distinta forma, por lo que puede haber discrepancias entre ellos.

## Canal Telegram para comunicar actualizaciones

Se ha creado este canal de Telegram para comunicar más fácilmente las actualizaciones de esta imagen: https://t.me/adam_image

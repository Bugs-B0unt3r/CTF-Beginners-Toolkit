# CTF Beginners Toolkit

Este repositorio contiene una colección de herramientas esenciales para principiantes en los CTFs. Están organizadas por categorías, con descripciones, enlaces oficiales y ejemplos de uso de comandos.

## Categorías

1. [Web Exploitation](#web-exploitation)
2. [Criptografía](#criptografía)
3. [Forense](#forense)
4. [Reversing](#reversing)
5. [Steganografía](#steganografía)
6. [Pwn](#pwn)
7. [Hardware Hacking](#hardware-hacking)
8. [GeoInt](#geoint)
9. [Redes](#redes)
10. [OSINT](#osint)
11. [Misc](#misc)
12. [Top 15 Plataformas para Jugar CTFs](#top-15-plataformas-para-jugar-ctfs)
13. [Top 3 Plataformas para Crear tu Propio CTF](#top-3-plataformas-para-crear-tu-propio-ctf)

---

## Web Exploitation

### 1. **[Burp Suite](https://portswigger.net/burp)**
   - **Descripción**: Herramienta de proxy y análisis para pruebas de seguridad web.
   - **Comando de uso**: 
     - Configura tu navegador para usar Burp Suite como proxy.
     - Intercepta solicitudes HTTP para modificar y analizar datos.

### 2. **[SQLMap](https://sqlmap.org)**
   - **Descripción**: Automatiza ataques de inyección SQL.
   - **Comando de uso**:
     ```bash
     sqlmap -u "http://example.com?id=1"
     ```

### 3. **[Wfuzz](https://github.com/xmendez/wfuzz)**
   - **Descripción**: Herramienta de fuerza bruta para descubrir archivos o rutas en servidores web.
   - **Comando de uso**:
     ```bash
     wfuzz -c -z file,/ruta/wordlist.txt --hc 404 http://example.com/FUZZ
     ```

### 4. **[Nikto](https://cirt.net/Nikto2)**
   - **Descripción**: Escáner de vulnerabilidades web.
   - **Comando de uso**:
     ```bash
     nikto -h http://example.com
     ```

### 5. **[Gobuster](https://github.com/OJ/gobuster)**
   - **Descripción**: Fuerza bruta para enumerar archivos y directorios en servidores web.
   - **Comando de uso**:
     ```bash
     gobuster dir -u http://example.com -w /ruta/wordlist.txt
     ```

---

## Criptografía

### 1. **[CyberChef](https://gchq.github.io/CyberChef/)**
   - **Descripción**: Herramienta web para operaciones de datos y criptografía.
   - **Comando de uso**: Usa su interfaz para aplicar operaciones de cifrado y descifrado.

### 2. **[Hashcat](https://hashcat.net/hashcat/)**
   - **Descripción**: Cracker de hashes con soporte para GPU.
   - **Comando de uso**:
     ```bash
     hashcat -m 0 -a 0 hash.txt wordlist.txt
     ```

### 3. **[John the Ripper](https://www.openwall.com/john/)**
   - **Descripción**: Herramienta de cracking de contraseñas.
   - **Comando de uso**:
     ```bash
     john --wordlist=wordlist.txt hash.txt
     ```

### 4. **[RSACTFTool](https://github.com/Ganapati/RsaCtfTool)**
   - **Descripción**: Automatiza ataques RSA como factorización.
   - **Comando de uso**:
     ```bash
     python3 rsactftool.py --publickey ./public.pem --decrypt ./ciphertext
     ```
### 5. **[FactorDB](http://www.factordb.com/)**
   - **Descripción**: Factoriza el valor N con el fin de obtener valores p y q.



---

## Forense

### 1. **[Autopsy](https://www.sleuthkit.org/autopsy/)**
   - **Descripción**: Plataforma forense para análisis de imágenes de disco.
   - **Comando de uso**: Abre una imagen de disco para explorar archivos eliminados o datos ocultos.

### 2. **[Volatility](https://www.volatilityfoundation.org/)**
   - **Descripción**: Herramienta de análisis de imágenes de memoria RAM.
   - **Comando de uso**:
     ```bash
     vol.py -f memoria.dmp windows.pslist
     ```

### 3. **[Foremost](http://foremost.sourceforge.net/)**
   - **Descripción**: Recupera datos de archivos eliminados.
   - **Comando de uso**:
     ```bash
     foremost -i imagen.img -o /salida
     ```

### 4. **[ExifTool](https://exiftool.org/)**
   - **Descripción**: Extrae metadatos de archivos.
   - **Comando de uso**:
     ```bash
     exiftool imagen.jpg
     ```
     
---

## Reversing

### 1. **[Ghidra](https://ghidra-sre.org/)**
   - **Descripción**: Herramienta de desensamblado y análisis de binarios.
   - **Comando de uso**: Abre el binario y usa herramientas de análisis automático para desensamblarlo.

### 2. **[dnSpy](https://github.com/dnSpy/dnSpy)**
   - **Descripción**: Desensamblador y depurador para aplicaciones .NET.
   - **Comando de uso**: Abre un archivo de .NET y navega por el código IL.

### 3. **[Radare2](https://github.com/radareorg/radare2)**
   - **Descripción**: Herramienta avanzada para ingeniería inversa y análisis de binarios.
   - **Comando de uso**:
     ```bash
     r2 -d ./archivo
     ```

### 4. **[x64dbg](https://x64dbg.com/)**
   - **Descripción**: Depurador para aplicaciones de 32/64 bits.
   - **Comando de uso**: Carga el binario y analiza el flujo de ejecución.

---

## Steganografía

### 1. **[Steghide](https://steghide.sourceforge.net/)**
   - **Descripción**: Oculta y extrae datos en imágenes y archivos de audio.
   - **Comando de uso**:
     ```bash
     steghide extract -sf imagen.jpg
     ```

### 2. **[zsteg](https://github.com/zed-0xff/zsteg)**
   - **Descripción**: Detección de datos ocultos en imágenes PNG/BMP.
   - **Comando de uso**:
     ```bash
     zsteg file.png
     ```

### 3. **[OpenStego](http://www.openstego.com/)**
   - **Descripción**: Software para ocultar archivos en imágenes.
   - **Comando de uso**:
     ```bash
     openstego -e -mf archivo.txt -cf imagen.png
     ```

---

## Pwn

### 1. **[Pwntools](https://github.com/Gallopsled/pwntools)**
   - **Descripción**: Biblioteca de Python para crear exploits.
   - **Comando de uso**: Instala con:
     ```bash
     pip install pwntools
     ```

### 2. **[ROPgadget](https://github.com/JonathanSalwan/ROPgadget)**
   - **Descripción**: Herramienta que permite encontrar gadgets ROP en binarios.
   - **Comando de uso**:
     ```bash
     ROPgadget --binary ./binary
     ```

### 3. **[GDB](https://www.gnu.org/software/gdb/)**
   - **Descripción**: Depurador GNU para revisar el comportamiento de programas y exploitarlos.
   - **Comando de uso**:
     ```bash
     gdb ./binary
     ```

---

## Hardware Hacking

### 1. **[Saleae Logic Analyzer](https://www.saleae.com/)**
   - **Descripción**: Herramienta de análisis lógico para monitorear señales digitales.
   - **Comando de uso**: Conecta el analizador a los pines de datos y captura las señales.

### 2. **[JTAGulator](https://www.digikey.com/en/products/detail/1501/1620-1027-ND/6086850)**
   - **Descripción**: Dispositivo para identificar interfaces JTAG en hardware.
   - **Comando de uso**: Conecta el JTAGulator a los pines del dispositivo y realiza un escaneo para identificar las conexiones JTAG.

### 3. **[Bus Pirate](http://dangerousprototypes.com/docs/Bus_Pirate)**
   - **Descripción**: Herramienta de análisis y comunicación con dispositivos de protocolo serial.
   - **Comando de uso**: Conecta el Bus Pirate a los pines del dispositivo y utiliza comandos como `I2C`, `UART`, etc., para interactuar.

---

## GeoInt

### 1. **[Google Earth](https://earth.google.com/web/)**
   - **Descripción**: Herramienta para análisis geográfico y visualización de mapas satelitales.
   - **Comando de uso**: Utiliza su interfaz web para buscar ubicaciones y obtener información geoespacial.

### 2. **[SAS Planet](https://www.sasgis.org/)**
   - **Descripción**: Herramienta de visualización de imágenes satelitales offline.
   - **Comando de uso**: Descarga imágenes de diferentes proveedores y realiza análisis sin conexión.

### 3. **[Geopy](https://geopy.readthedocs.io/en/stable/)**
   - **Descripción**: Biblioteca Python para geocodificación y geolocalización.
   - **Comando de uso**:
     ```bash
     pip install geopy
     ```

---

## Redes

### 1. **[Wireshark](https://www.wireshark.org/)**
   - **Descripción**: Analizador de paquetes de red para la captura y análisis de tráfico.
   - **Comando de uso**: Captura paquetes de red desde una interfaz y analiza su contenido.

### 2. **[Nmap](https://nmap.org/)**
   - **Descripción**: Escáner de red y puertos para descubrir servicios y hosts en una red.
   - **Comando de uso**:
     ```bash
     nmap -sV -p 1-65535 target.com
     ```

### 3. **[Aircrack-ng](https://www.aircrack-ng.org/)**
   - **Descripción**: Suite de herramientas para auditar redes WiFi.
   - **Comando de uso**:
     ```bash
     airodump-ng wlan0
     ```

---

## OSINT

### 1. **[theHarvester](https://github.com/laramies/theHarvester)**
   - **Descripción**: Herramienta de recolección de correos, subdominios y nombres de empleados mediante OSINT.
   - **Comando de uso**:
     ```bash
     theHarvester -d target.com -b all
     ```

### 2. **[SpiderFoot](https://www.spiderfoot.net/)**
   - **Descripción**: Herramienta automatizada para inteligencia de amenazas y OSINT.
   - **Comando de uso**:
     ```bash
     spiderfoot -s target.com
     ```

### 3. **[Shodan](https://www.shodan.io/)**
   - **Descripción**: Motor de búsqueda para dispositivos conectados a Internet.
   - **Comando de uso**:
     ```bash
     shodan search "webcamxp"
     ```

### 4. **[Whatsmyname](https://whatsmyname.app/)**
   - **Descripción**: Busqueda de cuentas activas por medio de un nombre de usuario.


---

## Misc

### 1. **[ctf-tools](https://github.com/zardus/ctf-tools)**
   - **Descripción**: Conjunto de scripts y herramientas para resolver CTFs.
   - **Comando de uso**: Instala las herramientas que necesites desde su colección.

### 2. **[Binwalk](https://github.com/ReFirmLabs/binwalk)**
   - **Descripción**: Extrae datos y analiza archivos binarios.
   - **Comando de uso**:
     ```bash
     binwalk -e archivo.bin
     ```

### 3. **[strings](https://man7.org/linux/man-pages/man1/strings.1.html)**
   - **Descripción**: Extrae texto legible de archivos binarios.
   - **Comando de uso**:
     ```bash
     strings archivo.bin
     ```

---

## Top 15 Plataformas para Jugar CTFs

1. **[Hack The Box](https://www.hackthebox.com)**
   - Plataforma popular con desafíos de pentesting y CTF.

2. **[TryHackMe](https://tryhackme.com)**
   - Ideal para principiantes y ofrece laboratorios interactivos para aprender seguridad.

3. **[CTFtime](https://ctftime.org)**
   - Directorio de competiciones de CTF en todo el mundo, con un sistema de clasificación.

4. **[Root-Me](https://www.root-me.org)**
   - Desafíos de hacking y CTFs con múltiples categorías.

5. **[picoCTF](https://picoctf.org)**
   - Diseñado para estudiantes, pero con retos que también desafían a jugadores más avanzados.

6. **[OverTheWire](https://overthewire.org)**
   - Juegos y retos para aprender seguridad informática y hacking.

7. **[HackThisSite](https://www.hackthissite.org)**
   - Una plataforma con desafíos de hacking ético y CTF.

8. **[CyberSecLabs](https://www.cyberseclabs.co.uk)**
   - Laboratorios interactivos enfocados en el pentesting y análisis de vulnerabilidades.

9. **[VulnHub](https://www.vulnhub.com)**
   - Ofrece máquinas virtuales vulnerables que puedes descargar y explotar.

10. **[W3Challs](https://w3challs.com)**
   - Plataforma con desafíos de hacking y seguridad web.

11. **[WeChall](https://www.wechall.net)**
   - Directorio de sitios de CTF con un sistema de clasificación y retos propios.

12. **[Hack This](https://www.hackthis.co.uk)**
   - Desafíos de hacking web, desde lo básico hasta lo avanzado.

13. **[0x0ffsec](https://www.0x0ffsec.com)**
   - Ofrece retos de seguridad informática, pentesting y criptografía.

14. **[Penetration Testing Practice Labs](https://pentestpractice.com)**
   - Entorno para practicar pruebas de penetración con desafíos tipo CTF.

15. **[CTF365](https://www.ctf365.com)**
   - Simulación de redes vulnerables para pruebas de penetración y CTFs.

---

## Top 3 Plataformas para Crear tu Propio CTF

1. **[CTFd](https://ctfd.io)**
   - Plataforma de código abierto para crear y organizar tus propios CTFs. Fácil de usar y personalizable.
   - **Cómo usar**: Despliega un servidor local o utiliza la versión en la nube para crear desafíos.

2. **[FBCTF](https://github.com/facebook/fbctf)**
   - Plataforma desarrollada por Facebook para organizar CTFs de forma sencilla.
   - **Cómo usar**: Instálalo en un servidor y crea desafíos personalizados.

3. **[RootTheBox](https://github.com/moloch--/RootTheBox)**
   - Juego CTF para aprendizaje interactivo, compatible con múltiples tipos de retos.
   - **Cómo usar**: Descarga e instala para personalizar y crear tu propio entorno de CTF.

---

¡Esperamos que este repositorio sea de gran ayuda para quienes están empezando en el mundo de los CTFs!

2...Magyar  27...Romana  54...English
====    Magyar   ====
ESP32 Chint Okosmérő Adatgyűjtő és Vektoros Fázisanalizátor
​Ez egy ESP32 alapú, nagyteljesítményű adatgyűjtő (Datalogger) és vizualizációs rendszer, amelyet kifejezetten Chint DSU666-H (és kompatibilis) intelligens háromfázisú fogyasztásmérőkhöz fejlesztettem ki. A projekt különlegessége az élő, böngészőben futó vektoros fázisdiagram, amely azonnal mutatja a fáziseltolódásokat és a napelemes visszatermelést.
​🚀 Főbb funkciók
​Valós idejű Modbus RTU kommunikáció: Fixen 1 másodpercenkénti mintavételezés az intelligens mérőből egy RS485-TTL átalakítón keresztül.
​Ipari Vektoros Fázisdiagram (Phasor Scope): Élő, böngészőoldali SVG-alapú vektoros diagram, amely mutatja a feszültség- és áramnyilak pontos fázisszögeit (Óramutató járásával megegyező ABC rotáció).
​Intelligens Dinamikus Skálázás (Auto-Range): Az áramnyilak automatikusan újraskálázzák magukat, ha bármelyik fázisáram meghaladja a 10 Ampert (felkerekítve 15A, 20A, stb. lépcsőkben), így kis terhelésnél és nagy áramoknál is jól látható a grafika.
​Függetlenített SD kártyás logolás: A webes élő felület 1 másodpercenként pörög, miközben az SD kártyára írás külön ciklusban, a beállított mintavételi idő szerint (pl. 5-10 másodpercenként) történik CSV formátumban. Ez maximálisan kíméli az SD kártya élettartamát.
​Teljes Webes Vezérlőpult: Élő böngészős naplózás (Live Browser Log), CSV fájlok letöltése és törlése közvetlenül a webfelületről, Wi-Fi menedzsment és OTA (vezeték nélküli) szoftverfrissítési támogatás.
​Napelemes termelés követése: Automatikus fázisszög- és előjel-számítás. Visszatermelés esetén az aktív teljesítmény (Watt) negatív értéket vesz fel, és az áramnyilak 180 fokkal elfordulnak, vizuálisan jelezve a hálózatba történő táplálást.
​🛠️ Hardver felépítés & Bekötés
​1. RS485 / Modbus oldal (Mérő -> Átalakító)
​Chint 24-es kapocs (A / RS485+) -> RS485 modul A+
​Chint 25-ös kapocs (B / RS485-) -> RS485 modul B-
​2. TTL oldal (RS485 Átalakító -> ESP32)
​VCC -> ESP32 5V / Vin
​GND -> ESP32 GND
​TXD -> ESP32 RX2 (GPIO 16)
​RXD -> ESP32 TX2 (GPIO 17)
​3. SD Kártya Olvasó (SPI Busz)
​MOSI -> GPIO 23
​MISO -> GPIO 19
​SCK / CLK -> GPIO 18
​CS (Chip Select) -> GPIO 5
​💻 Szoftver verzió
​Jelenlegi stabil verzió: v4.3 (Optimalizált hurokidővel és szeparált SD-író ciklussal).
====    Romana   ====
ESP32 Chint Smart Meter Datalogger și Analizor de Faze Vectoriale
​Acesta este un sistem performant de colectare a datelor (Datalogger) și vizualizare bazat pe ESP32, dezvoltat special pentru contoarele inteligente trifazate Chint DSU666-H (și compatibile). Caracteristica specială a proiectului este diagrama vectorială de fază care rulează live în browser, arătând instantaneu defazajele și injecția de energie de la panourile fotovoltaice.
​🚀 Funcții principale
​Comunicare Modbus RTU în timp real: Eșantionare fixă la fiecare 1 secundă din contorul inteligent prin intermediul unui convertor RS485-TTL.
​Diagramă vectorială de fază (Phasor Scope): Diagramă vectorială live în browser bazată naiv pe SVG, care arată unghiurile exacte de fază ale vectorilor de tensiune și curent (Rotație ABC în sensul acelor de ceasornic).
​Scalare dinamică inteligentă (Auto-Range): Vectorii de curent se rescalează automat dacă curentul de fază depășește 10 Amperi (rotunjit în pași de 15A, 20A etc.), oferind o grafică clară atât la sarcini mici, cât și la curenți mari.
​Logare pe card SD independentă: Interfața web live rulează la fiecare secundă, în timp ce scrierea pe cardul SD se face într-un ciclu separat, conform timpului de eșantionare setat (ex. la fiecare 5-10 secunde) în format CSV. Acest lucru protejează durata de viață a cardului SD.
​Panou de control web complet: Jurnalizare live în browser (Live Browser Log), descărcarea și ștergerea fișierelor CSV direct din interfața web, management Wi-Fi și suport pentru actualizări software wireless (OTA).
​Monitorizarea producției fotovoltaice: Calcul automat al unghiului de fază și al semnului de putere. În caz de injecție în rețea, puterea activă (Watt) devine negativă, iar vectorii de curent se rotesc cu 180 de grade, indicând vizual livrarea de energie în rețea.
​🛠️ Structură Hardware & Conexiuni
​1. Partea RS485 / Modbus (Contor -> Convertor)
​Borna Chint 24 (A / RS485+) -> Modul RS485 A+
​Borna Chint 25 (B / RS485-) -> Modul RS485 B-
​2. Partea TTL (Convertor RS485 -> ESP32)
​VCC -> ESP32 5V / Vin
​GND -> ESP32 GND
​TXD -> ESP32 RX2 (GPIO 16)
​RXD -> ESP32 TX2 (GPIO 17)
​3. Cititor de carduri SD (Bus SPI)
​MOSI -> GPIO 23
​MISO -> GPIO 19
​SCK / CLK -> GPIO 18
​CS (Chip Select) -> GPIO 5
​💻 Versiune Software
​Versiunea stabilă curentă: v4.3 (Cu timp de rulare optimizat și ciclu de scriere pe SD separat).
ESP32 Chint Smart Meter Datalogger & Vector Phasor Analyzer
​This is an ESP32-based high-performance datalogger and visualization system developed specifically for Chint DSU666-H (and compatible) smart three-phase energy meters. The highlight of this project is the live, browser-based vector phasor diagram that instantly displays phase shifts and solar power injection.
​🚀 Key Features
​Real-time Modbus RTU Communication: Fixed 1-second interval sampling from the smart meter via an RS485-to-TTL converter.
​Industrial Vector Phasor Scope: Live, browser-side SVG-based vector diagram showing exact phase angles of voltage and current vectors (Clockwise ABC rotation).
​Smart Dynamic Scaling (Auto-Range): Current vectors automatically rescale if any phase current exceeds 10 Amps (rounding up to 15A, 20A, etc.), ensuring optimal graphic clarity under both low and high loads.
​Independent SD Card Logging: The web UI updates every second, while SD card data logging runs in a separate cycle based on the configured sample time (e.g., every 5-10 seconds) in CSV format. This maximizes the lifespan of the SD card.
​Full Web Control Panel: Live browser logging (Live Browser Log), download and deletion of CSV log files directly from the web interface, Wi-Fi management, and OTA (over-the-air) wireless software update support.
​Solar Production Tracking: Automatic phase angle and power sign calculation. In case of grid injection, active power (Watt) takes a negative value, and current vectors rotate by 180 degrees, visually indicating power feedback into the grid.
​🛠️ Hardware Setup & Pinout
​1. RS485 / Modbus Side (Meter -> Converter)
​Chint terminal 24 (A / RS485+) -> RS485 module A+
​Chint terminal 25 (B / RS485-) -> RS485 module B-
​2. TTL Side (RS485 Converter -> ESP32)
​VCC -> ESP32 5V / Vin
​GND -> ESP32 GND
​TXD -> ESP32 RX2 (GPIO 16)
​RXD -> ESP32 TX2 (GPIO 17)
​3. SD Card Reader (SPI Bus)
​MOSI -> GPIO 23
​MISO -> GPIO 19
​SCK / CLK -> GPIO 18
​CS (Chip Select) -> GPIO 5
​💻 Software Version
​Current stable version: v4.3 (Optimized loop time with an independent SD writing cycle).

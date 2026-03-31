# 🛸 VORTEX // P2P Distributed Handpan DAW

![Version](https://img.shields.io/badge/version-1.0.0-blueviolet)
![License](https://img.shields.io/badge/license-MIT-green)
![Technology](https://img.shields.io/badge/tech-WebRTC%20%7C%20WebAudio-orange)

**VORTEX** is een experimenteel, gedistribueerd muziekinstrument gebouwd met **WebRTC** en de **Web Audio API**. Het stelt twee gebruikers in staat om in realtime samen te spelen in een gesynchroniseerde sequencer-omgeving, met een focus op de harmonische klanken van een F# Celtic Minor Handpan.

---

## 🌟 Kernfuncties

-   **Real-time P2P Synchronisatie:** Dankzij WebRTC DataChannels worden sequencer-stappen en live interacties met een latentie van milliseconden overgedragen.
-   **Master/Slave Architectuur:**
    -   **Master:** Heeft de volledige controle over de sequencer, toonladders en beschikt over de **Session Recorder**.
    -   **Slave:** Ontvangt realtime updates en speelt synchroon mee zonder configuratie-overhead.
-   **Multi-Scale Engine:** Schakel tussen *F# Celtic Minor*, *D Kurd*, en *C Akebono*. Toonladders worden direct gesynchroniseerd tussen beide peers.
-   **High-Fidelity Web Audio:** Een custom additive synthese-engine bootst de boventonen van een fysieke handpan na.
-   **Ingebouwde Recorder:** De Master kan de volledige sessie (video + audio) vastleggen met één druk op de knop.
-   **Acoustic Space Control:** Ingebouwde Reverb en Master Volume sliders voor lokale audio-optimalisatie.

---

## 🛠️ Hoe het werkt

### 1. Connectie (Signaling)
Het instrument gebruikt een WebSocket-signaling server (bijv. in Node-RED of Node.js) om de initiële WebRTC-handshake (Offer/Answer/ICE) uit te voeren. Zodra de tunnel open is, verloopt al het verkeer direct tussen de browsers (**Peer-to-Peer**).

### 2. Audio Engine
De klank wordt gegenereerd door 4 harmonische sinus-oscillatoren per noot, met een specifieke exponentiële decay om het karakteristieke "metaal-geluid" te vangen.

### 3. Sequencer
Een 9-staps circulaire sequencer loopt synchroon op beide schermen. De Master verstuurt `STEP` objecten via het DataChannel om te garanderen dat beide instrumenten op exact dezelfde beat spelen.

---

## 🚀 Installatie & Gebruik

1.  **Clone de repository:**
    ```bash
    git clone [https://github.com/jouw-gebruikersnaam/vortex-handpan.git](https://github.com/jouw-gebruikersnaam/vortex-handpan.git)
    ```

2.  **Signaling Server:**
    Zorg dat je een WebSocket server hebt draaien op `ws://127.0.0.1:1880/vortex`. (Of pas het IP-adres in de code aan naar je eigen server).

3.  **Open het instrument:**
    Open `vortex_instrument.html` in twee verschillende browser-tabs of op twee verschillende computers.

4.  **Verbinden:**
    -   Klik op beide schermen op **1. INIT ENGINE**.
    -   Klik op één scherm op **2. INITIATE (MASTER)**.
    -   De Slave verbindt automatisch.
    -   Klik op **START P2P RESONANCE** om de muziek te starten.

---

## 🎛️ Bediening

| Knop / Slider | Functie |
| :--- | :--- |
| **Randomize** | Genereert een willekeurig ritmisch patroon op beide schermen. |
| **Clear** | Wist het huidige patroon. |
| **Scale Selector** | Verandert de toonsoort (Alleen Master). |
| **Acoustic Space** | Voegt dromerige galm toe aan je lokale audio. |
| **REC / CAPTURE** | Start een scherm- en audio-opname (Alleen Master). |

---

## 📜 Licentie

Dit project is uitgebracht onder de MIT-licentie. Voel je vrij om de code aan te passen en je eigen instrumenten toe te voegen!

---

*Gemaakt met passie voor digitale audio en P2P technologie.*

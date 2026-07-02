# AM Radio Receiver

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Institution](https://img.shields.io/badge/Institution-Polytechnique_Montréal-blue)

A fully functional, custom-built AM Radio Receiver designed from scratch on a breadboard. This project blends electronic design with electromagnetic field theory to successfully capture local AM broadcasting frequencies (540 kHz to 1600 kHz). 

Designed with a special **Montreal Canadiens (Bleu, Blanc, Rouge)** theme, the ultimate goal of this build was to achieve a clean signal at **TSN 690 kHz** to listen to live hockey broadcasts.

## 👥 The Team
* Edouard Prud'Homme
* Frédéric Pimentel

## 🎥 Video Demonstration
*(https://www.youtube.com/watch?v=ummKtrk6xlA)*

## 🧠 Theoretical Operation (The 4 Stages)
1. **Reception (Faraday's Law):** A custom 40x40 cm wooden loop antenna captures variations in the ambient magnetic field, inducing an electromotive force.
2. **Tuning / Filtering (LC Circuit):** A parallel LC tank circuit isolates the target frequency. 
3. **Demodulation (Envelope Detector):** A Germanium diode with a low forward voltage drop rectifies the weak AM signal, stripping the high-frequency carrier wave.
4. **Amplification:** An LM386 audio amplifier IC boosts the isolated audio signal to drive standard headphones.

## 📐 Design Choices & Engineering Math
To hit our target of **TSN 690 kHz** reliably, we had to work within the strict constraint of our variable capacitor, which had a limited range of **10 pF to 100 pF**. 

* **Antenna Geometry:** We constructed a 40cm x 40cm wooden frame using brass screws (to avoid magnetic interference).
* **Inductance ($L$):** Winding exactly 20 turns of copper wire yielded a measured inductance of **~870 µH**.
* **Capacitance ($C$):** Using the resonance formula $f = \frac{1}{2\pi\sqrt{LC}}$, targeting 690 kHz required a capacitance of exactly **61 pF**. 

This brilliant mathematical alignment placed our target frequency directly in the center of our variable capacitor's range, allowing for highly stable and accurate tuning.

## 🛠️ Hardware & Tools
* **Antenna:** Custom wooden frame (40x40cm), 20 turns of copper wire, brass screws.
* **Tuning:** 10-100 pF Variable tuning capacitor.
* **Demodulation:** Germanium Diode.
* **Amplification:** LM386 Audio Amplifier IC.
* **Schematics:** Designed in [KiCad](https://www.kicad.org/).

## 📁 Repository Contents
* `/Hardware` - Contains the KiCad schematic (`.sch`) and project files.

## 🚀 How to Replicate
1. Open the `.sch` file in KiCad to view the complete wiring diagram.
2. Ensure the middle pin (rotor) of the variable capacitor is wired to common ground to eliminate "hand capacitance" interference while tuning.
3. Keep the breadboard wires as short as possible to reduce parasitic capacitance, which severely limits high-frequency reception (like CJAD 800 kHz).

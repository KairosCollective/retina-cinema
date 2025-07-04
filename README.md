<p align="center">
    <img src=https://github.com/user-attachments/assets/7907accf-39e7-464e-b647-d7435a873bda width=250>
</p>


# ReTiNA-Cinema: TouchDesigner Patches for Adaptive Neuro-Augmented Cinema

This repository contains the **TouchDesigner project** and **configuration files** used for the [ReTiNA-Cinema](https://github.com/KairosCollective/retina-cinema) system described in our paper:

> **Introducing ReTiNA-Cinema: Real-Time Neuro-Augmented Cinema via Generative AI**
> *(Paper link coming soon)*

**ReTiNA-Cinema** transforms movie visuals in real-time, using viewers' EEG brain signals to modulate AI-driven cinematic effects, supporting both single-user and multi-user (hyperscanning) modes.

---

## Instructions
1. Install [**TouchDesigner**](https://derivative.ca/download) and [**goofi-pipe**](https://github.com/dav0dea/goofi-pipe?tab=readme-ov-file#installation) by following the installation instructions at the respective links.
2. Download the repository files by cloning or downloading the ZIP.
3. Unlock and download the StreamDiffusion Node on dotsimulate's Patreon: [StreamDiffusion Node](https://www.patreon.com/posts/122151912?collection=565003).
4. Open the `retina-cinema.toe` file in TouchDesigner and drag the StreamDiffusion Node into the project.
5. Connect the StreamDiffusion node's first input to the MoviePlayer's TOP output, and the StramDiffusion output to the input of the SDOutput node as shown in the screenshot:
<p align="center">
    <img src=https://github.com/user-attachments/assets/5f8b64da-b406-45f2-bb2e-4b6a4fe4c89b width="900">
</p>

6. Configure the parameters of the StreamDiffusion node as shown in the following screenshot:
<p align="center">
    <img src=https://github.com/user-attachments/assets/63fafb7b-4d74-4fc1-b64d-2c4465826b46 width="500">
</p>

7. Start goofi-pipe and load the desired patch:
    - `goofi-pipe single-user.gfi` for modulation with a single EEG stream
    - `goofi-pipe multi-user.gfi` for modulation with two simulatenous EEG streams (hyperscanning)
8. Start streaming your EEG via LSL and select the correct LSL source and stream names in the LSLCLient node(s) inside the goofi-pipe interface.
9. Start the StreamDiffusion model (in TouchDesigner).
10. Enjoy ReTiNA-Cinema!

---

## Included Files

* **`retina-cinema.toe`** The main TouchDesigner project file that implements the adaptive cinema system.
* **`single-user.gfi`** Single-user goofi-pipe patch for feature extraction from a single EEG stream.
* **`multi-user.gfi`** Multi-user (hyperscanning) goofi-pipe patch for feature extraction from two EEG streams.

---

## Requirements

* [**TouchDesigner**](https://derivative.ca/download) for real-time video processing
* [**goofi-pipe**](https://github.com/dav0dea/goofi-pipe?tab=readme-ov-file#installation) for EEG feature extraction
* [**StreamDiffusion Node**](https://www.patreon.com/posts/122151912?collection=565003) for real-time AI visuals (by [dotsimulate](https://dotsimulate.com/))

---

## License

This project is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).

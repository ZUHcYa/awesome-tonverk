# ☁️ Pseudo-Granular Synthesis using LFOs

![OS Requirement](https://img.shields.io/badge/OS-1.50%2B-success?style=flat-square&logo=elektron)
![Category](https://img.shields.io/badge/Category-Sound_Design-purple?style=flat-square)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-yellow?style=flat-square)

Turn any static sample into a moving, evolving cloud of texture by modulating the Sample Start point with a randomized LFO. This is the "classic" Digitakt granular trick.

## Prerequisites
* A sample with rich harmonic content (e.g., a pad or a vocal drone).
* **AMP** Decay set to infinite (or long release).

---

## Step-by-Step Guide

### 1. Source Setup
Load your sample onto a track.

> [!NOTE]
> **Version Difference:**
> * **OS 1.50+:** Set the Machine to **Repitch** or **Werp** for best results.
> * **Legacy OS:** Use standard **One Shot** playback.

### 2. Configure the LFO
Go to the **LFO** page (`LFO` button) and apply the following settings:

| Parameter | Value | Description |
| :--- | :--- | :--- |
| **DEST** | `SMP: Start` | Modulates where the sample starts playing. |
| **WAVE** | `RND` (Random) | Picks a new start point every trigger. |
| **MODE** | `HOLD` | Keeps the value static per trigger. |
| **MULT** | `BPM 2K` | Fast modulation speed. |

### 3. The "grain" size
Adjust the playback length to create the "grains".
1.  Go to the **SRC** page.
2.  Set `LEN` (Length) to a very low value (approx. **1.00 - 5.00**).
3.  Set `LOOP` to **ON**.

### 4. Play it
Hold a trig or record a long note. You should hear the sample "skipping" through different parts of the file randomly.

---

## Signal Flow (How it works)

```mermaid
graph LR
    A[LFO 1 Random] -- Modulates --> B(Sample Start Point)
    C[Sequencer Trig] --> D[Amp Envelope]
    B --> E[Audio Output]
    D -- Gates --> E
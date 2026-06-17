# Lofi Room - Audio Reactive Bedroom Scene Plugin for Blender
 
> A Blender add-on that brings a cozy, lofi aesthetic bedroom to life through music.  
> Load a track. The plugin separates its stems. Assign drums, bass, guitars, piano and vocals, and melody to objects in the room. 

## Concept
Inspired by lofi YouTube channel — [Lofi Girl](https://www.youtube.com/channel/UCSJ4gkVC6NrvII8umztf0Ow$0) - this plugin ships a **stylised bedroom scene** that reacts to any music file you give it.

![Alt text of the image](https://as2.ftcdn.net/jpg/05/72/19/99/1000_F_572199937_H1U1S2caf3FxdJmBQpAIqyHLIwbHTl2A.jpg)

## Functionality

Unlike generic audio visualisers that respond to raw frequency energy, Lofi Room uses **demucs (open-source neural source separation transformer)** to extract the actual instrument stems from your track such as drums, bass, guitar, piano, vocals, and melody and maps each one to a different object or effect in the scene. Lamps pulse with the drum hits and fireworks when there is a high beat. Curtains breathe with the melody. The room shifts between day and night.

## Planned Features
### Core — Minimum Viable Product
- **Pre-built bedroom scene** — stylised bed, window, curtains, desk lamp, floor lamp, bookshelf; lofi aesthetic, deliberately not photorealistic
- **Audio file input** — load `.mp3` or `.wav` from the N-panel
- **Neural stem separation via [Demucs](https://github.com/facebookresearch/demucs)** — splits any track into six stems: Drums · Bass · Guitar · Piano · Vocals · Other (melody/pads) 
- **Per-stem amplitude analysis** — frame-by-frame envelope extracted from each stem, resampled to match the Blender timeline
- **Object–stem assignment UI** — N-panel list: select any scene object, assign a stem, choose an effect (glow / shake / scale / colour shift)
- **Keyframe baking** — convert all stem-driven mappings into standard Blender F-curves with one button
- **Lamp glow on drums** — emission strength of lamps follows drum transients and hits

- **Bass room ambience** — subtle camera shake or object vibration follows bass amplitude
- **Day / Night toggle** — switches HDRI, sun lamp colour/intensity, and curtain wind weight
- **Fireworks particle system** — triggered in night mode on drum hits, visible through the bedroom window

### Stretch Goals
- **Curtain flutter on melody** — shape key blending driven by the "Other" stem (pads, keys)
- **Vocal-driven colour temperature** — shift the scene's warm/cool balance with vocal energy
- **Live microphone / stream input** — react to real-time audio (replaces Demucs with frequency-band fallback for live mode)

### Future Work
- **Node Editor** - Node Editor where users can link stems to objects in the scene
- **Custom Scene** - Users can dynamically link objects in their custom scene

### Related Plugins and Literature

- Défossez, A., Usunier, N., Bottou, L., & Bach, F. (2019). *Music source separation in the waveform domain.* arXiv:1911.13254 — the original Demucs architecture
- Rouard, S., Massa, F., & Défossez, A. (2023). *Hybrid transformers for music source separation.* ICASSP 2023 — the `htdemucs` model used in this plugin

- [Sound React](https://blender-addons.org/sound-react-addon/) | This animates any animatable Blender property from frequency presets but not the stems
- [Sound Nodes](https://blender-addons.org/sound-nodes/)| Geometry Nodes integration — Sound Info, Spectrogram, and Chromagram nodes

### References
 [Demucs (Meta / Facebook Research)](https://github.com/facebookresearch/demucs) | State of the art music source separation; `htdemucs` model separates into drums, bass, guitar, piano, vocals and other
 
 [Lofi Girl — lofi hip hop radio](https://www.youtube.com/watch?v=jfKfPfyJRdk) —  visual reference for the bedroom aesthetic and fixed camera framing




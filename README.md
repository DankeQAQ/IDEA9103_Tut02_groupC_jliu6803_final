# Audio-Reactive Circular Pattern Visualization  
---

## How to Interact with the Work  

To experience my work, open `index.html` in your browser (preferably Chrome).  
- Click the **Play/Pause** button in the top-left corner to start or stop the music.
- When the music is playing, the large colored circular patterns on the canvas will dynamically grow and shrink in sync with the volume of the audio.
- If the music is paused or stopped, the animation also pauses and all visuals return to their original state.
- No additional mouse or keyboard interaction is required for the main animation.

---

## My Personal Approach to the Animation Group Code  

I started with our group’s original p5.js code, which generates a grid of multi-layered, colorful circles using a custom `RingPattern` class.  
My focus was on **integrating sound responsiveness** directly into these primary circles, so that the core visual identity is preserved while becoming interactive with music.  
Unlike simply adding unrelated effects, my approach embeds audio reactivity into the scale transformation of each main ring, making the entire composition pulse together with the beat.


---

## What Drives My Code: Audio, Interaction, Perlin Noise or Time?  

My code is **driven by audio**, specifically the real-time amplitude (loudness) of the music file loaded in the sketch.  
- I used the `p5.Amplitude` analyzer to measure the music’s volume at each animation frame.
- There is no use of Perlin noise, interaction, or time-based autonomous animation in this version.
- The visual effect is purely responsive to the audio’s volume.


---

## What Visual Properties are Animated, and How? What Makes it Unique?  

The **unique animated property** in my code is the scaling (size) of the main concentric circles (rings).  
- When the music gets louder, all the large circles expand smoothly; when it is softer, they shrink.
- All inner details, colors, and patterns maintain their relative proportions due to scaling.
- Compared to other group members who might animate color, opacity, rotation, or selective segment display, my work is distinct in that **the entire primary structure breathes as one** in response to music.


---
## Inspiration for Making the Animation Dynamic  

My inspiration comes from several places:
- The Week 12 p5.js tutorial on sound-reactive graphics, where ellipses change size with music amplitude.
- Audio-visual performances by Tarik Barri, whose abstract visuals closely follow live audio.
- These references led me to focus on amplitude-based global scaling, making the entire pattern pulse in time with the music.


---

## Technical Notes and References  

- I use `p5.Amplitude` to get the current RMS volume (`amp.getLevel()`) of the music.
- The scale factor is mapped from the volume to a value (e.g. between 1.0 and 2.5).
- In the main draw loop, all main ring radii are multiplied by this scale factor for real-time size change.
- When music stops, animation freezes (no more size change).
- All code is original, but logic is based on the official [p5.js Sound Reference](https://p5js.org/reference/p5.sound/) and class tutorial code.

---

## Explanation of Significant Changes to the Group Code  

- I **modified the `RingPattern` class** so that all its drawing logic accepts a `scale` parameter, ensuring clean animation.
- I **removed unrelated circle effects** to prevent visual clutter.
- I restructured the draw logic so that animation only occurs when the music is playing; otherwise, the image stays static.

---

## Note on Submission and Iterations

This project was completed over three main iterations, with each iteration reflecting feedback and incremental improvements in both code and interaction design.

Iteration 1: Basic Visual Structure and Static Animation

- In the first version, I implemented the basic visual framework, including all ring patterns and ellipses based on the group’s initial design.

- The animation at this stage was purely static: the graphics would render on the canvas, but there was no interaction or audio-driven behavior.

- I ensured all visual elements matched the style guide and initial group discussions.

Iteration 2: Introduction of Audio Integration

- The second iteration introduced p5.js sound libraries to the project.

- I added a Play/Pause button to control audio playback, and loaded the audio file in the preload() function.

- I created amplitude and FFT analyzers and connected them to the audio input.

- At this stage, I experimented with linking amplitude data to the scaling of ring patterns, so that the main circles could visually react to sound.

- I also fixed timing issues to ensure that the animation only responded when audio was actually playing.

Iteration 3: Polishing, Bug Fixes, and Documentation

- The final iteration focused on refining the interaction experience and cleaning up the code.

- I improved the logic so that ring animation and scaling only occurred when the music was playing; otherwise, all visuals remained static.

- I optimized the animation effect to make the circles’ scaling smoother and more visually pleasing, avoiding distracting visual flicker.

- All new code sections relating to audio animation and Play/Pause control were clearly commented in both English and Chinese for group readability.

- The README and comments were improved to give a clear, professional description of what was changed and why, and how to interact with the finished work.
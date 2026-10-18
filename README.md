# 🌲 Forest Audio

A 3D forest level with a fully implemented audio design, built with Blueprints and MetaSounds in Unreal Engine 5. This was made for CA3, and the focus is on using sound to build a calm, ethereal atmosphere and to make the world feel alive.

## 📦 Technologies

- `Unreal Engine 5`
- `Blueprints`
- `MetaSounds`
- `Sound Cues`
- `Sound Attenuation`
- `Physics Materials`

## ⚙️ Features

Here's what you can hear and experience in the forest:

- **Surface-Based Footsteps**: A line trace 200 units downwards detects the surface type through physics materials. Grass plays light, quick footsteps. Stone plays harsh, powerful ones with a longer delay, and movement is slowed by 50% to match.

- **Forest Ambience**: A looping ambience made of wind, birds, crickets, and music, each with its own modulator for pitch and volume variation. The inner radius and falloff fade the sound in as you enter the forest and bring it to full volume in the thick of it.

- **Buzzing Bugs**: A MetaSound for bugs with randomised, interpolated pitch shifts, a biquad filter, and a volume parameter. Each bug has public variables for volume and pitch, so different bug types sound different and can be edited all at once.

- **Spatialized Sound**: Bugs use an attenuation asset with a small inner radius (100) and a falloff of 1,200, so you can track them down by ear. One bug overrides the attenuation so you can hear it when approaching its pillar.

- **Moving Pillars**: A trigger box on the ramps calls the pillar's move function, which plays a timeline-driven movement with attached sound. Each pillar has its own move duration, and slower ones emphasize the weight of the rock.

- **Audio Looper**: A reusable Blueprint that plays a one-shot sound at random intervals, with public variables for the sound, volume, pitch, min/max delay, and attenuation. It's used for the tree creaking, with some placed high up in the trees to draw the player's eyes upwards.

- **Air Absorption and Occlusion**: Tree creaks lose their high frequencies with distance and are blocked when other trees are in the way.

- **Main Menu**: Hover sounds feel like pushing leaves and branches aside, and click sounds feel like throwing or walking past stones. The menu is created at game start in the game mode base and destroyed on start or quit.

## 🔨 The Process

I started with footsteps. I used a line trace and physics materials to detect the surface under the player, and set up two arrays of sounds so a random one is picked each step. Then I matched the footstep delay and movement speed to how each surface should feel.

Next, I built the forest ambience. I placed the loop so it fades in gradually, with a reduced volume around the stone pillars and full volume deeper in the forest. I applied modulators to the wind, birds, crickets, and music to add variation, and lowered the music so it didn't overpower the rest.

After that, I created the bug sounds. I made a MetaSound for the buzzing and exposed its parameters, then added an audio component to the bug Blueprint that sets them on begin play. I used an attenuation asset to give the bugs spatialization so they can be found by ear.

Then I worked on the pillars with a trigger box, a movement timeline, and an attached sound with attenuation. I set different move durations to match their size.

I also made the audio looper Blueprint for random one-shot sounds and used it for the tree creaking, adding air absorption and occlusion.

Finally, I built the main menu sounds and hooked the menu up in the game mode base.

## 📚 What I Learned

During this project, I got a much better understanding of how sound shapes the way a game feels.

### 🦶 Footsteps and Physics Materials:

- **Surface Detection**: Using line traces and physics materials to play different sounds per surface, and how sound and movement can work together to communicate weight.

### 🎛️ MetaSounds:

- **Procedural Audio**: Building the bug buzz with random triggers, interpolation, and a biquad filter, and exposing parameters so each bug can be different.

### 🎧 Spatialization:

- **Attenuation**: Tuning the inner radius and falloff so players can locate sounds, plus air absorption and occlusion for realism.

### 🌳 Ambience Design:

- **Variation and Balance**: Using modulators and volume balancing to keep the ambience from getting repetitive or overpowering.

### 🧱 Reusable Blueprints:

- **Production Efficiency**: Making the audio looper and public variables so many objects can be edited at once, which would save a lot of time in a full level.

### 📈 Overall Growth:

This project taught me to think about audio as a tool for guiding the player, creating curiosity, and reinforcing scale and atmosphere, not only as background noise. It also taught me to build flexible systems that scale to a bigger level.

## ✔️ How can it be improved?

- Add more surface types, like dirt, wood, and water, with their own footsteps.
- Add more bug types to fill out the full level.
- Add more music and ambience layers that react to the player's location.
- Add a settings menu with volume controls.
- Add more reusable audio Blueprints.

## 🚚 Running the Project

To run the project in your local environment, follow these steps:

1. Clone the repository to your local machine.
2. Install Unreal Engine 5 (use the same version the project was created with).
3. Open the `.uproject` file with Unreal Engine.
4. Press Play in the editor to explore the level.

## 📽️ Video

[**Watch the Gameplay Showreel!**](https://www.youtube.com/watch?v=Crc4AthdQYA) (🎧Headphones recommended)

# Plush Studies

Procedural stuffed toys built as single HTML files with native **WebGPU + WGSL**. No libraries, textures or external assets.

| Study | File | What it does |
| --- | --- | --- |
| No. 018, Red-Eyed Plush Frog | `frog.html` | Crouched tree frog: hops, catches a fly with a satin tongue, hugs your fingertip, live configurator for pile and colours |
| No. 017, Plush Squid | `squid.html` | Floating squid: breathing mantle, jets, striking tentacles, clinging arms, felt suckers |

## Tech

- **Rendering**: WebGPU with hand-written WGSL shaders. Fur is drawn with shell rendering (10 to 14 offset layers), alpha-to-coverage and 4x MSAA. A procedural comb map stores nap direction and lay.
- **Physics**: XPBD on the CPU. Soft body made of particle rings with distance constraints, shape matching and a volume constraint. Limbs are rod chains. Pose attraction recoil is fed back into the body so momentum is conserved.
- **Interaction**: ray casting against the mesh for the Hand, Finger and Comb tools.
- **Performance**: adaptive quality (render scale, shell count, MSAA), early discard of empty fur fragments, 60 fps cap.

## Run

Open `index.html` through any static server, or use GitHub Pages. WebGPU must be enabled. On Linux Chrome, turn on `chrome://flags/#enable-unsafe-webgpu` and `#enable-vulkan`.

## Controls

`1` Hand, `2` Finger, `3` Comb, `J` jet or hop, `R` fluff up, `Q` quality, `K` configurator (frog). Drag empty space to orbit, scroll to zoom.

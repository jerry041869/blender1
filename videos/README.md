# SlimeSweep V3 — Blender use demonstration

Two seven-second scenes: cleaning between mechanical keyboard keycaps, and cleaning a narrow gap beneath furniture. Each scene shows approach, gel compression, contact, dust adhesion and withdrawal. Particles and lint remain on the surface until contact, then move with the tool. The mechanism and adhesion are keyframed concept demonstrations rather than physical performance tests.

Delivery: H.264 MP4, 800 × 450 pixels, 24 fps, Chinese step captions, silent. The combined version is 14 seconds. Blender rendered the 3D scenes; FFmpeg denoises, interpolates the rendered frames and adds captions.

Source model: the SlimeSweep V3 concept model in this workspace. Animation materials simplify the transparent reservoir to improve readability and rendering cost. No real filmed footage or hand interaction is included.

Outputs:
- `SlimeSweep_keyboard.mp4`
- `SlimeSweep_crevice.mp4`
- `SlimeSweep_usage_demo.mp4` (two scenes joined)
- `SlimeSweep_keyboard_animation.blend`
- `SlimeSweep_crevice_animation.blend`
- `animate.py` (generator; uses `/workspace/output/slimesweep/SlimeSweep_V3.blend`)

Regenerate with `SWEEP_SCENE=keyboard blender -b -t 5 --python animate.py` and `SWEEP_SCENE=crevice blender -b -t 5 --python animate.py` from this directory. Scenes contain 112 timeline frames at 16 fps; alternate frames are rendered to PNG with Cycles and interpolated to 24 fps in final video encoding. Chinese captions are added during MP4 encoding.

# 38





## 40 - Tune-A-Video

**Problem：**

1. using full attention in space-time inevitably leads to quadratic growth in computation
2. employing a naive fine-tuning strategy that updates all the parameters can jeopardize the pre-existing knowledge of T2I models and hinder the generation of videos with new concepts.

**Contribution：**

1. a sparse spatio-temporal attention mechanism that only visits the first and the former video frame
2. an efficient tuning strategy that only updates the projection matrices in attention blocks.
3. DDIM inversion that use the inverted latent as initial noise to produce temporally-coherent videos featuring smooth movement.



## 39 - Rerender

**Problem：**

1. train a video model on large-scale video data 
   1. require significant computing resources
   2. incompatible with existing off-the-shelf image models
2. fine-tune image models on a single video
   1. less efficient for long videos
   2. overfitting to a single video may also degrade the performance of the original models
3. zero-shot methods that require no training，during the diffusion sampling process, cross-frame constraints are imposed on the latent features for temporal consistency. However, current cross-frame constraints
   1.  limited to global styles
   2. unable to preserve low-level consistency

**Contribution :**

1. use optical flow to apply dense cross-frame constraints
   1. the previous rendered frame serving as a low-level reference
   2. the first rendered frame acting as an anchor
2. key frame translation
   1. pre-trained image diffusion models for generating key frames
   2. with hierarchical cross-frame constraints
3. full video translation
   1. temporal-aware patch matching and frame blending to propagate frames

**Something Need To Think Again : **

1. Cross-frame attention is limited to global style. To constrain the cross-frame local shape and texture consistency, we use optical flow to warp and fuse the latent features.
2. Fidelity-oriented image encoding
3. Structure-guided inpainting
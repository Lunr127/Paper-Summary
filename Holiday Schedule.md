# 39





## Tune-A-Video

**Problem：**

1. using full attention in space-time inevitably leads to quadratic growth in computation
2. employing a naive fine-tuning strategy that updates all the parameters can jeopardize the pre-existing knowledge of T2I models and hinder the generation of videos with new concepts.

**Contribution：**

1. a sparse spatio-temporal attention mechanism that only visits the first and the former video frame
2. an efficient tuning strategy that only updates the projection matrices in attention blocks.
3. DDIM inversion that use the inverted latent as initial noise to produce temporally-coherent videos featuring smooth movement.


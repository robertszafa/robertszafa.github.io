---
title: "Accelerating Biological Sequence Alignment Using a GPU"
collection: publications
# permalink: /publications/
date: 2021-06-01
venue: 'Bachelor of Science Honours Dissertation'
---
For my undergraduate final year project I used CUDA to achieve high GPU occupancy for the Needleman-Wunsch global sequence alignment algorithm and Smith-Waterman local sequence alignment algorithm.
An important feature of the implementation is that it is not restricted by the size of the GPU global memory. This is achieved by dividing the problem into smaller chunks, with each GPU SM working on one chunk at a time. There is a synchronisation routine between SMs - this is needed to exchange values at the boundaries of the chunks. A big portion of the dissertation examines how the speedup scales with the number of SMs.
I also make the argument that for sequence alignment it makes sense to have both the GPU and CPU work concurrently if there is a sequence of alignments coming in - sequence alignment consists of two parts, one parallel, one sequential. I show experimental results confirming this argument.
[Dissertation](/files/Accelerating_Biological_Sequence_Alignment_with_GPU.pdf) [Code](https://github.com/robertszafa/sequence-alignment-gpu)

# TODO

## CosmicTagger v1.x

> **Note**: Conversion of CT to the various machines is meant to be a tutorial as to how
to convert a model.

### Cerebras CT

Cerebras cannot support CT and UNets in general as of 4/25/23.

### Graphcore CT

Alex has been very busy with conferences, etc.

He ran CT but, it ran on the CPU.  He has stated that it may need to be completely written
using, I can't remember which, Poplar or PopArt.  If that is necessary, Venkat should
make the call.

### Groq CT

4/27/23 Grog is working on their compiler.  I think they said they were getting
almost 50 steps/sec for 1K by 2K images.  Check with Corey but, I think that is quite good.

### Habana CT

This is done.

Repo:    https://github.com/argonne-lcf/user-guides.git
Branch:  feature/Habana002-DNP
File:    docs/ai-testbed/habana/CosmicTagger-Conversion.md

### SambaNova CT

SN has a highly-engineered version of CT.

They are working to support CT OOB, Out-Of-Box.

## Cerebras

Repo:    https://github.com/argonne-lcf/user-guides.git
Branch:  Talk to Bill.

## Graphcore

Repo:  https://github.com/argonne-lcf/user-guides.git

When you change back to 3.2, use virtual-environments.md from the commit a4ce3b5598f4d6feee7ca58accde1a6a0ea84244 "virtual-environments.md with 3.2 edits."

Need to finish docs/ai-testbed/graphcore/profiling.md.
I have not been able to get Graph Analyser to connect.  Alex has been pinged.

## Groq

Repo:   https://github.com/argonne-lcf/user-guides.git
Branch: feature/Groq001-DNP

## Habana

Repo:  https://github.com/argonne-lcf/user-guides.git
Branch:  feature/Habana002-DNP

## SambaNova

Repo:  https://github.com/argonne-lcf/user-guides.git

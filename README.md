# MemoryRetrieval

A `c++` based retrieval system for binary embeddeded *memories*

Memories are **not** stored within the program (e.g. vector) but are instead chunked and stored as files.

This allows the system to run without a large amount of system Ram being taken up (especially when there would be 100ks of memories).

## Chunking
Chunking allows Memories to be distributed and much more efficent compared to reading/writing/deleting one large file

$$ \frac{t}{f} = c$$

Where $t$ is the total of memories, $f$ is the amount of files you want per chunk and $c$ is the amount of files per chunk


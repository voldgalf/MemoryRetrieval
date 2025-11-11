# External Memory With Flash Storage

## What does this solve?

LLMs (Large Language Model) have a context window, which is the amount
of tokens they can remember before forgetting. This system allows an LLM
to retrieve and create Memories, essentially expanding the memory of the
model (without the RAM costs of a large context window).

## Storage

The *Memories* are not stored on the computer itself, but are read from
a storage device (such as an SD Card). This allows the Memories to be:

-   Interchangeably read between different *Memory Systems*

-   Securely & safely stored in the event of computer's complete failure

Each Memory is stored as binary, which gives numerous benefits
including:

-   Removal any need for parsing (text-based)

-   Efficient storage of large Memories, compared to ASCII storage

However, the Memories should **not** be stored a singular file, as this
is *incredibly* slow compared to multiple files. A solution is chunk the
memories into different files. This negates many problems such as

-   speed inefficiency for Create Read Update Delete (CRUD) operations

-   the risk of a singular file being corrupted corrupted every memory

## The Memory System

Each chunked file is **not** read into system memory together as this
would quickly consume the system's memory once the memory count is high
enough.

Instead, once given a phrase to recall a memory relating towards; the
following logic occurs for each Memory File.

1.  A Memory File is read into system memory

2.  The read memories are filtered into memories that are related to the
    given phrase

3.  the filtered memories are sent to a list

4.  the Memory File is removed from memory, as it is no longer required

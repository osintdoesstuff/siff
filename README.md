# siff
Simple Interchange File Format. It's like IFF, but dumbed down!

Specification version 4. What happened to 0, 1, 2, and 3? The world may never know.
## 1. Legal Gibberish

This specification is free to use by anyone. Don't blame me if it steals your pet rock\[1\]

## 2. By Far The Simplest Spec You've Ever Seen

The SIFF format is comically simple. Well, it stands for **Simple** Interchange File Format i dunno what you expected\[2\]. 

Note that SIFF is fully little-endian\[3\].

The file header is like this:

```psudeo
byte[2] magic = [0xED, 0xDI] // 2 bytes
byte version = 4 // we're on v4 right now, v0, v1, v2, and v3 were just prototypes dw
uint16 chunkCount = 69 // or something i dunno, this is also 2 bytes in case you can't read
```

The chunk header looks like this:

```psudeo
byte[6] chunkID // 6 bytes if it wasn't obvious
uint32 dataLength = 69
byte[dataLength] data
```

Despite the psudeocode examples, chunkCount and dataLength aren't meant to always be 69 in case you can't read\[3\]

It works i guess.

## 3. Not My Fault

* The name SIFF is dumb because it's derived from IFF and i had to add something to it
* ED D1 is picked as the file header because basically every other one is used.

## 4. Footnotes

1. I am not responsible for any pet rock thefts caused by the SIFF file format
2. Seriously, what did you expect?
3. Little-endian despite some architecture's protests

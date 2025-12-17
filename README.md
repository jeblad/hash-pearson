# hash-pearson

![stability-wip](https://img.shields.io/badge/stability-work_in_progress-lightgrey.svg?style=for-the-badge)
![GitHub issues](https://img.shields.io/github/issues-raw/jeblad/hash-pearson?style=for-the-badge)

## Scope

Pearson non-cryptographic hash function

From the paper [Fast Hashing of Variable-Length Text Strings](http://cs.mwsu.edu/~griffin/courses/2133/downloads/Spring11/p677-pearson.pdf) ([archived](https://web.archive.org/web/20120704025921/http://cs.mwsu.edu/~griffin/courses/2133/downloads/Spring11/p677-pearson.pdf)) by _Peter K. Pearson_ with additional edits by [jeblad](mailto:jeblad@gmail.com) (Dec 13, 2025).

The core of the Pearson hash algorithm is fast execution on processors with integer registers. The implementation requires few instructions, and a lookup table containing permutated values from 0 to one less the size of the table. It produces a hash value that is strongly dependent on every byte of the input.

The original version uses a lookup table of 256 values to be particularly efficient on processors with 8 bit registers, by completely exhausting the available space. This version is adapted to use larger registers and variant size of the lookup table.

The Pearson hash is particularly well suited when a completely uniform distribution is necessary, together with repeatability.

The current implementation is meant for a specific use case, and might not be generally usable.

## Usage

The _hash-pearson_ library is in a single header file. Simply grab the file and put it wherever it is needed, or pull the repo as a submodule.

```bash
wget https://raw.githubusercontent.com/jeblad/hash-pearson/refs/heads/main/hash-pearson.h
```

or

```bash
git submodule add git@github.com:jeblad/hash-pearson.git path-to-submodule
```

The _path-to-submodule_ would typically be something like `include/hash-pearson` if you're in the project folder.

If you're adding the _hash-pearson_ as a submodule, then pull an updated version.

# SiloBuilder

[![Build Status](https://travis-ci.org/jgoldfar/SiloBuilder.svg?branch=master)](https://travis-ci.org/jgoldfar/SiloBuilder)

This is an example repository showing how to construct a "builder" repository for a binary dependency.  Using a combination of [`BinaryBuilder.jl`](https://github.com/staticfloat/BinaryBuilder.jl), [Travis](https://travis-ci.org), and [GitHub releases](https://docs.travis-ci.com/user/deployment/releases/), we are able to create a fully-automated, github-hosted binary building and serving infrastructure.

This repository is notable in that it shards its builds over multiple runs on Travis, each run building a single target Silo binary.  On a git tag, the resulting binaries are uploaded, one by one, to a GitHub release, and once all have uploaded a final job is run to checksum them all and construct a final `build.jl`.

We will be installing 

    https://wci.llnl.gov/content/assets/docs/simulation/computer-codes/silo/silo-4.10.2/silo-4.10.2-bsd.tar.gz
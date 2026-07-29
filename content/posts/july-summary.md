+++
title = "July summary"
date = "2026-07-28T01:00:00-03:00"
showFullContent = true
readingTime = false
hideComments = false
+++

Since I started working full-time with open source development in April, I wanted to make more of what I do public. This post is a summary of my recent work, most of it available on github, but some of it only exists in my office/workshop, those I can show pictures and thoughts.

## Software

### On hold / next up

- Search space tuning for ASICs
  - https://github.com/256foundation/mujina/discussions/72
  - https://github.com/jayrmotta/mujina/tree/fix/bm13xx-hcn-nonce-range

- Running Mujina on the S19J Pro+

### PI based fan speed controller
https://github.com/256foundation/mujina/pull/33

I've been keeping this PR synced with `main` waiting for further reviews and the eventual merge.

### Configuration

We have been discussing what would be an appropriate config system for Mujina as it is a core feature, the spec (MIP-0001) has an open PR looking for reviews. In parallel I have started a slice of the whole spec as a way to kickstart the full implementation, but also to build some momentum and enable some powerful features coming up.

For example we envision having a "reconciliation loop" to allow clients to set targets (like wattage consumption) and have the firmware automatically tune itself to achieve that goal. It's a cool foundational project for Mujina.

Links:
  - https://github.com/256foundation/mujina/pull/36
  - https://github.com/256foundation/mujina-mips/pull/1
  - https://github.com/256foundation/mujina/issues/83
  - https://github.com/256foundation/mujina/pull/84


### StratumV2 support
https://github.com/256foundation/mujina/pull/65
https://github.com/256foundation/mujina/discussions/54#discussioncomment-17636900

I heard this is currently being reviewed by Ryan, and we also had an interesting development with the BIP-323 coming with bitcoin-core v32 which raises the theoretical ceiling to 72PH/s for header-only mining, which changes some of our foundational decisions to go for extended channels.

Other than that I've been thinking about our abstractions as I had a brief discussion with @b-rowan about it, currently transport and protocol are mixed which means that for SV1 we would have to duplicated code when introducing SV1+SSL. Perhaps a good refactoring opportunity or trap in disguise?

### Mujina+bitaxe over wifi
https://github.com/256foundation/mujina/discussions/47

This is just this silly idea I had as a "QoL" for myself as I didn't want the Bitaxe to be always connected to my computer over USB. I have spent a few hours exploring the problem space and it's really big.

But I've been part of discussions considering to adopt bitaxe-raw into Mujina and I think if we had this and a smoother path to flash it, it could be more than a simple convenience for developers and become an actual alternative to ESP-miner.

## Hardware

### On hold / next up
- Test the 3 non-official control boards with my S19J Pro+ hash boards

### Assemble a NerdNOS

I wanted something I wouldn't feel bad if I fucked up beautifuly so I sourced the components for 2 units of this build along the components for the Gamma. I'm mostly waiting for the components to be delivered.

Do we have a PCB for this one? Need to check that!

I might do a 3d printing sprint and include the case for this one as projects are piling up already.

### Assemble a Bitaxe Gamma

Also waiting for components but also need to adjust the PCB gerber with some cool image to sign the build, might go for a lil surprise. Then order it from JLPCB along with the stencils.

### Replace thermal paste on the S19J Pro+ for research/dev

Getting this device to run has been a long activity as a lot of ground knowledge and infrastructure had to be developed. Now I am able to run it but it's overheating, so I ordered some tools and the special paste to do some maintenance.

I've been watching some YouTube videos and considering ZeusBTC's course, but still a bit skeptical/uncertain if I should pay for that course or just "wing" it with AI, community, etc.

### Building a DIY solder reflow oven
https://www.youtube.com/watch?v=SD2NSzEQYDI

We are almost there, missing the two power plugs which I will purchase in local stores. The 3D printing will be a challenge as the cutouts for the japanese plugs used by the author of the video, but we'll figure something out.

I'm excited for that this enable us to do after, all sorts of devices we can get our hands on schematics. I already have my eyes on the SolarBit and some more advanced mining devices like the Gamma Hex.

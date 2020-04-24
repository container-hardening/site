+++
Categories = ["mission"]
Description = "Mission Statement"
Tags = ["development", "linux", "containers"]
title = "Mission"
date = "2015-01-01"

+++

**Table of Contents:**

- [Mission Statement](#mission-statement)
- [Principles](#principles)
- [Get Involved](#get-involved)
- [Areas of Focus](#areas-of-focus)
- [Education](#furthering-education-of-hardening-containers)
- [FAQ](#faq)

# Mission Statement

This project will focus on hardening of Linux containers. It will help
contribute patches to the [Kernel Self Protection
Project](https://kernsec.org/wiki/index.php/Kernel_Self_Protection_Project)
that evolve the primitives in the Linux kernel used by containers (namespaces,
cgroups, etc) to be more secure. This will include brainstorming,
designing and implementing ways to future proof namespaces et all in the kernel.

This will benefit all container runtimes by keeping the focus on improving the
kernel in the subsystems used by containers. We will strive to push the entire
container ecosystem to be more secure by fixing the ground they are built upon.

Much like the Kernel Self Protection Project we think of security [beyond
fixing bugs](https://lwn.net/Articles/662219/). Fixing bugs is important and we
will do that as well but the main value will come from finding ways to future
proof namespaces with features that will eliminate undisclosed vulnerabilities.
At this point, it is no longer enough to try to fix all the bugs within
namespaces, we must try to find ways to make them more secure from the very
foundation.

We will also work to help educate people on how to use the features of
Capabilities, Seccomp, AppArmor, and SELinux to harden their containers.
We will try to find ways to make them more accessible to more users.

# Principles
(same as that of the [Kernel Self Protection
Project](https://kernsec.org/wiki/index.php/Kernel_Self_Protection_Project#Principles)
but copied here)

A short list of things to keep in mind when designing self-protection features:

- Patience and an open mind will be needed. We're all trying to make Linux
  better, so let's stay focused on the results.
- Features will be more than finding bugs. Should be active at run-time to catch
  previously unknown flaws.
- Features will not be developer-"opt-in". When a feature is enabled at build
  time, it should work for all code built into the kernel (which has the
  side-effect of also covering out-of-tree code, like in vendor forks).

# Get Involved

We welcome you! Check out instructions for getting involved with
the [Kernel Self Protection Project](https://kernsec.org/wiki/index.php/Kernel_Self_Protection_Project#Get_Involved).

Be sure to checkout [Areas of Focus](#areas-of-focus) below to see if you
have anything specific you would like to help with. If not, don't worry we
can find something that piques your interest together.

# Areas of Focus

**Preventing Privilege Escalations in User Namespaces**

First things first, this is the most obvious area we should focus on.

We should split up the various parts of the kernel and closely audit the
interactions with user namespaces. The fundamental problem seems to be that not
many people have inspected user namespaces and the various interactions
with other parts of the kernel.

The attack surface is very large, let's divide up the various subsystems and knowledge
share our findings. We can then use this to innovate on well-informed solutions.

# Furthering Education of Hardening Containers

We need better education around how to lock down your containers by
utilizing the LSMs and kernel features integrated into these runtimes.

**Fun ways to educate:**

- [contained.af](https://contained.af): A game about capabilities and syscalls.

**Work being done to help people write security profiles for their containers:**

- [high-level security profile generator proposal](https://gist.github.com/jessfraz/3a84023ff85471696ee33a20031b9e7b): Proposal
  for a high-level security profile generator that would be easier for developers to write.
- [bane](https://github.com/jessfraz/bane): A better way to write AppArmor profiles (prototype).

# FAQ

### Who are we?

Some of the few believers that containers may actually contain. Join us :)

### Why is this not a part of the Open Container Initiative?

The [Open Container Initiative](https://www.opencontainers.org/)
states very clearly in their mission they only
strive to create "standards" for containers. Most of the work in the Open
Container Initiative is focused on specifications for container runtimes. This
project is entirely out of scope for that. We will be focusing on securing the
primitives that make up a container, not a "json schema specification" for how
you tell a container runtime your settings. We will be working towards
protecting the very brick and mortar containers are built with in the kernel
rather than the implementation details of the runtimes themselves.

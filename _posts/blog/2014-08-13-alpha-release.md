---
title: First alpha release!
author: Tristan
---

The first 1.0 alpha release is ready after a great rework.

My main focus on this release was [issue #78](https://github.com/filicious/core/issues/78).

Here is a short summary what I have done in the last [49 commits](https://github.com/filicious/core/compare/0.9.1...1.0-alpha1)
from the 0.9.1 to the new 1.0-alpha1 release.

First I have not removed the Filesystem class, as I planned.
While overwork the API, I find out that splitting the adapters from the
filesystem is a good idea to split the public from the internal API.
Most of the API still exists as before.

**I have removed:**

- The cache classes (that are never used yet)
- The global configuration object (each adapter must store its own configuration).
- The symlink, mime and hash functions from the File class (these are now plugins)
- The AggregateAdapter class (it is replaced by the MountAdapter class)
- Some dead code

**I have added:**

- Filesystem plugin support (symlinks, mime and hash functions are now provided through plugins).
- Added event support.
- Added stream support directly into the Filesystem class.

I improved and cleaned the public and private API and moved some convenience methods into the Util or the new
Validator class. After all, the new build is working again :-)
https://travis-ci.org/filicious/core/builds/32444809

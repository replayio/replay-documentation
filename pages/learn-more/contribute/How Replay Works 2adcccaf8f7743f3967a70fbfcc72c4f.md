# How Replay Works

<aside>
💡 This document is somewhat outdated. While we are working on this, please refer to [Replay for New Contributors](Replay%20for%20New%20Contributors%2075b0cf0cf7234e3597dbdf14e82d4f4e.md) instead.

</aside>

[Replay.io](http://Replay.io) is the first time-travel debugger for runtimes like the browser and Node.

We wrote some blog posts outlining how it worked, covering the basics of how we record OS syscalls, use “effective determinism” to minimize the data needed, and turn browser processes in the cloud into a public API that can be used to introspect a program’s behavior:

1. [Overview](https://medium.com/replay-io/how-replay-works-5c9c29580c58)
2. [Recording and Replaying](https://medium.com/replay-io/recording-and-replaying-d6102afee273)
3. [Effective Determinism](https://medium.com/replay-io/effective-determinism-54cc91f5693c)
4. [Inspecting Runtimes](https://medium.com/replay-io/inspecting-runtimes-caeca007a4b1)

There’s also a recent set of posts talking about the “effective determinism” aspect in more detail, including how we can replay the full browser behavior with a relatively small recorded set of input data, and how we investigate “runtime mismatch” errors internally:

- [How to debug an Effectively Deterministic Time Travel Debugger? (Seriously.. how?!)](https://medium.com/replay-io/how-to-debug-an-effectively-deterministic-time-travel-debugger-seriously-how-ba4d59965b7a)
- [Cross Your Fingers and Hope to Crash](https://medium.com/replay-io/cross-your-fingers-and-hope-to-crash-d13e648e5567)

For some additional details, see these docs pages:

[Our approach for source maps ](How%20Replay%20Works%202adcccaf8f7743f3967a70fbfcc72c4f/Our%20approach%20for%20source%20maps%201f5afb2cf5ad45a488369e65a821039d.md)

[How programmatic recordings work](How%20Replay%20Works%202adcccaf8f7743f3967a70fbfcc72c4f/How%20programmatic%20recordings%20work%2006310eae305742a497435a63fd6673fc.md)

For examples of how the Replay Protocol API is used, see the actual Replay DevTools client repo, the Replay Protocol API Examples repo, and the Protocol API docs

- [https://github.com/replayio/devtools](https://github.com/replayio/devtools)
- [https://github.com/replayio/Protocol-Examples](https://github.com/replayio/Protocol-Examples)
- [https://static.replay.io/protocol/](https://static.replay.io/protocol/)
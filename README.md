# **Orchestra**

**Async-friendly parallel execution for CPU-bound tasks.**
Orchestra provides an awaitable interface over a multiprocess engine, allowing Python applications to run heavy computations in parallel without blocking the event loop.

It is designed for projects that rely on asynchronous orchestration but still require real CPU throughput — scientific tools, simulation engines, async servers, large workflows, or any environment where tasks must coexist with a responsive async runtime.

---

## **✨ Features (Planned)**

* **Async-first API**
  Submit a task with `await orchestra.run(...)` — no thread pools or hacks.

* **True parallelism**
  CPU-bound tasks run in separate processes, bypassing the GIL.

* **Predictable task model**
  Clear boundaries between async orchestration and worker execution.

* **Graceful worker lifecycle**
  Clean startup, shutdown, and failure handling.

* **Serialization-aware**
  Future support for structured, safe task encoding (e.g., `msgspec`).

* **Portable**
  A consistent, cross-platform approach to CPU-bound async work.

---

## **Why Orchestra?**

Python’s `asyncio` is excellent for I/O-bound concurrency — but it blocks hard on CPU-heavy functions.
Existing solutions either:

* rely on threads (which don’t bypass the GIL),
* expose low-level executors,
* or behave inconsistently across platforms.

Orchestra aims to provide a **simple, ergonomic layer** specifically for async applications that need real CPU parallelism, without forcing users into heavyweight distributed frameworks or fragile multiprocessing code.

If your async code needs to stay responsive *and* compute efficiently, Orchestra fills that gap.

---

## **🧠 Design Philosophy**

* **Explicit > implicit**
  Users always know if something runs locally or in a worker.

* **Safe boundaries**
  Workers are isolated and predictable; errors propagate cleanly.

* **Small surface area**
  A compact API that hides internal complexity.

* **Scalable**
  Capable of expanding to dynamic worker pools or specialized worker types.


## **📜 License**

This project is released under the **Apache License 2.0**.
See the `LICENSE` and `NOTICE` files for details.
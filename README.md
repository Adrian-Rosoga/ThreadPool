ThreadPool
==========

Fork of https://github.com/progschj/ThreadPool.

This version doesn't use std::shared_ptr in the enqueue method, hence using less memory and avoiding the reference count increment/decrement overhead.

Its performance should be better when there are many threads enqueuing work items concurrently.

C++14's capture by value-move (Lambda Capture Expressions feature) allows for a different way to make use of unique_pointer instead of shared_ptr. As C++14 support is patchy at the time of writing I preferred instead to make use of C++11 features only.

The class function_wrapper is taken almost verbatim from Anthony William's book "C++ Concurrency in Action" (https://www.manning.com/books/c-plus-plus-concurrency-in-action).

The idea is to eventually merge these changes into the original progschj/ThreadPool.

# WHAT THE sVH?!

A tiny diagnostic page to visualize and debug how browsers calculate svh (small viewport height) on first load and after resize or orientation changes.

# 🧠 What It Does

This page measures what the browser thinks `100svh` equals in pixels — both width and height — and displays the results directly on-screen.

It's useful for spotting inconsistencies in how different browsers or webviews handle viewport height units like svh, lvh, and dvh, especially on mobile (e.g., Safari, Chrome on iOS, in-app browsers, etc).

## How It Works

1. A hidden `<div>` is created with height: 100svh; width: 100%;
2. The script measures its pixel dimensions via `getBoundingClientRect()`
3. The script re-measures automatically on `resize` and `orientationchange`.

## Try It

Observe the displayed `svh` pixel value before and after interacting (scrolling, resizing, rotating).

## Why It Exists

Some browsers — especially mobile webviews and Safari — misreport viewport height before the user interacts (e.g., the URL bar collapses).
svh, lvh, and dvh were introduced to fix this, but implementations vary.
This tool shows what your browser actually computes, so you can debug layout shifts or vh-based bugs easily.

## Tech Details

* No frameworks. Pure HTML, CSS, and JS.
* No dependencies.
* Automatically updates on:
  * `resize`
  * `orientationchange`
* Uses CSS feature detection for svh support (commented out by default, can be re-enabled if needed).

## Example Use Case

Run this page inside:

* Mobile Safari
* Chrome for Android
* An in-app browser (Instagram, TikTok, etc.)

Compare the measured pixel values before and after the first user interaction.
You'll often see the height shrink or grow — proving the svh bug in that environment.

## License

MIT © Marcus Michaels
Use, modify, and share freely.

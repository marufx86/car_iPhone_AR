# 3D Car in AR

A 3D car in augmented reality for iPhone and iPad. Scan the cover image and the car appears. Runs in Safari with AR Quick Look, no app needed.

**Live:** https://car-i-phone-ar.vercel.app/
**Repo:** https://github.com/marufx86/car_iPhone_AR

## Use

1. Show the cover on a second screen, or print it 12 cm wide.
2. On iPhone or iPad, open the live page and tap **Open in AR**.
3. Aim the camera at the cover. The car appears.

Needs an AR-capable iPhone or iPad with Safari. Other devices see a "Needs iPhone or iPad" notice.

## How it works

- `Car-final.reality` is a RealityKit scene anchored to an image (the cover, 11.8 cm wide). The car fades in when the camera recognises it.
- `index.html` links to the scene with `<a rel="ar">`, which Safari on iOS and iPadOS opens in AR Quick Look. The link's first child must be an `<img>`.
- `vercel.json` serves the `.reality` file as `model/vnd.reality` with `Content-Disposition: inline`.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Landing page and AR Quick Look link |
| `Car-final.reality` | AR scene (3D car, image anchor) |
| `book-cover.jpg` | AR marker. Must match the image embedded in `Car-final.reality` |
| `vercel.json` | Headers for the `.reality` file |

Static site, no build step. To change the marker, re-export the `.reality` with the new image anchor and replace `book-cover.jpg` with the same image.

## Author

Built by [@marufx86](https://github.com/marufx86).

# Changelog

## Unreleased

## 0.1.16

- Added compact Preview playback controls with pause, scrubbing, frame stepping, speed selection, keyboard shortcuts, and draggable A/B range handles with automatic repeat.
- Preserve playback state between original/result revisions and adaptive variants, with optional inspection beyond Stop markers.
- Added proportional Preview scaling from a corner handle outside the banner, with a zoom indicator, one-click reset, and scrolling for enlarged banners.
- Apply Width resizing relative to the full source image so cropped regions retain the same scale; clarify Width tool help and cover cropped-image rendering.
- Show per-stage firmware export progress and elapsed time, yield between targets to keep the panel responsive, and report the active stage on failure.
- Bound TinyPNG requests with timeouts and handle interrupted responses while preserving original images on failure.

## 0.1.15

- Isolate Adaptive Frame players to their own variant layers so neighboring states cannot reset animated text matte positions or displace gradient clipping.

## 0.1.14

- Fixed text Track Matte references after automatic outline conversion so gradient shapes remain clipped to text, including disabled matte sources, shared sources, duplicate layer names, and changing layer indices.
- Preserve even-odd letter holes in exported text matte contours while text and gradient layers animate independently.

## 0.1.13

- Added a shared CONTROL_ADAPTIVE guide Null with composition-wide centering controls and independent width/height thresholds in adaptive JS and CSS exports; preserve controller settings when applying or clearing layer constraints.
- Added Preserve Minimum Size, enabled by default, to keep adaptive Position and Scale calculations at or above the original banner dimensions independently on each axis.
- Keep content visible beyond the centered banner edges once a centering threshold is reached, and restore clipping below the thresholds or when switching to a variant without centering.
- Changed new layer constraint defaults to Scale Strength 0 and Max Scale 1.

## 0.1.12

- Enable image atlases by default in Always mode with JPEG quality 75 for projects without saved settings; preserve explicit project and firmware overrides.

## 0.1.11

- Added project and preview Width sharpness controls (0–200%, default 50%; explicit saved settings are preserved), using alpha-safe Unsharp Mask after actual downscaling for separate images and atlases across JS/CSS, adaptive and firmware exports; preview rebuilds reuse unsharpened pixels and publish matching ZIP snapshots.
- Improved Width image sharpness with alpha-safe Lanczos3 resizing, lossless prepared pixels for JPG atlases and native-pixel atlas rendering without an extra fractional bitmap resize.
- Compact atlas pages with a bounded MaxRects width search to avoid unnecessarily long strips and reduce empty space without changing JPEG quality or image resolution.

## 0.1.10

- Added JPG atlases for opaque images and PNG atlases for transparent images across normal/adaptive exports, JS/CSS previews and firmware releases, preserving layer geometry, masks, effects and animation.
- Added project atlas settings and firmware size-group overrides with Off/Auto/Always modes, adjustable JPG quality, complete ZIP size comparison and safe fallback to separate images.
- Optimize only completed atlas pages through TinyPNG when atlases are used; skip source-image requests, cache successful compression and optimize individual images only when exporting separate files.
- Added browser preview controls for local atlas rebuilding, TinyPNG image/atlas compression, Terser JS minification, original/result comparison and ZIP downloads matching the displayed version.
- Preserve compound AE fills and even-odd holes in JS/CSS exports, including independent contour animation inside shared SVG paths.
- Increased exported Gaussian and backdrop blur strength by 30% for closer visual matching with AE, consistently for static values and animation.

## 0.1.9

- Added composition selection by folder with Select all, Clear selection, and bulk Add selected actions.
- Preserve collapsed composition groups, individual selections, and scroll position across panel refreshes; reset selection when switching projects.

## 0.1.8

- Added Crop and Width tools for export-time image cropping and fixed pixel widths, preserving layer geometry and animation in export and preview.
- Preserve prepared PNG/JPEG bytes and distinct crop/resize variants through asset normalization, adaptive export, ZIP packaging and size accounting.
- Added independent horizontal/vertical Position Strength and maximum composition dimensions for adaptive position and scale constraints in AE, HTML and firmware CSS exports.
- Preserve rotated Sticky Shape contours and sample evaluated offset geometry when it cannot be represented by rectangle animation tracks.

## 0.1.7

- Included bundled TinyPNG keys in release archives and both installers so image optimization works on fresh installations.

## 0.1.6

- Fixed Sticky Shape drifting during Position and Rotation animation under rectangle parents in HTML export and preview, regardless of layer order.
- Removed duplicate parent animation tracks while preserving easing, hold interpolation, and Sticky offset animation.

## 0.1.5

- Fixed loopOut cycle and pingpong animation in HTML export and preview when keyframes are outside the composition timeline, preserving original key times, values, easing, and loop phase.

## 0.1.4

- Moved the shared GitHub connection settings to Settings → Sync, with labeled repository and token fields, token visibility controls, and advanced folder settings.
- Added copying and pasting of complete sync settings, including the GitHub token, with format validation and manual clipboard fallbacks for CEP.
- Added a dismissible sync setup reminder on each panel launch until configured, setup badges, and direct settings links from Project Sync and Firmware Sync.
- Separated saved-settings feedback from repository connection checks and prevented sync operations before setup.

- Preserved rotated Sticky Shape contours and offset animation instead of replacing them with an enlarged bounding rectangle.

## 0.1.3

- Updated the panel layout with board side panels, a reorganized tools dock and clearer tool controls.
- Improved adaptive variant selection and scaling to fit width-fluid and height-fluid banners to their container.
- Added a command to create the Banners folder directly from the panel.
- Fixed precomp layer masks and Mask Path animation applying scale, rotation and position twice in export and preview.
- Preserved trailing zeros in integer SVG coordinates when exporting animated paths and masks.
- Fixed Sticky Shape geometry animation under scaled text parents with X/Y motion in HTML export and preview.
- Added the Set Stop marker tool to create or move a composition timeline marker with configurable completed playback cycles: Stop(0) stops on the first arrival, Stop(1) after one complete cycle, and so on.
- Added Stop marker support to HTML and adaptive banner exports, with precise frame stopping and cycle tracking across pause, speed changes, seeking and restart.
- Preserved unrelated timeline markers and grouped Stop marker changes into one Undo step; invalid and duplicate Stop markers now produce export warnings.

## 0.1.2

- Added macOS and Windows installers with development checkout protection and rollback on installation errors.

## 0.1.1

- Added update checks, release notes, version downloads and skip-version controls in Settings.
- Added automatic versioning and GitHub release packaging with npm run release.
- Fixed Sticky Shape offset export for scaled layers.
- Fixed rectangular layer masks and grouped temporary export actions into one Undo step.
- Fixed TinyPNG key failover when a key reaches its compression limit.

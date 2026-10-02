# Changelog

## Unreleased

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

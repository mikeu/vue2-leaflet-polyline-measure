# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).


## [1.2.0] - 2020-01-18

### Added
- Example page for viewing the component and its events in action.
- Instructions in readme for launching the demo locally.

### Changed
- Switched package entry point directly to Vue component, removing the need for a
build process.


## [1.1.1] - 2020-01-09

### Security
- Updated Vue CLI to resolve several vulnerabilities in older dependencies.


## [1.1.0] - 2020-01-09

### Added
- Documentation about handling measurement events via the containing map object.

### Changed
- Updated Leaflet.PolylineMeasure to version 2019-11-15, which includes additional
events as well as various bug fixes.


## [1.0.0] - 2019-04-25

### Added
- This changelog.

### Changed
- Updated the README.

### Removed
- No longer emits a `ready` event on mount.


## [0.0.3] - 2019-04-24

### Added
- CSS import from Leaflet.PolylineMeasure to correctly style buttons and tooltips.
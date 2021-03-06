#Change Log
This project adheres to [Semantic Versioning](http://semver.org/).

This CHANGELOG follows the format listed at [Keep A Changelog](http://keepachangelog.com/)

## [Unreleased][unreleased]
- Adds Ignore option to exclude mount point(s) based on regular expression

## [1.0.3] - 2015-10-25
### Changed
- Adds Ignore option(s) to check-disk-usage.rb
- Adaptive thresholds

### Adaptive Thresholds

This borrows from check_mk's "df" check, which has the ability to
adaptively adjust thresholds for filesystems based on their sizes.

For example, a hard threshold of "warn at 85%" is quite different
between small filesystems and very large filesystems -  85% utilization
of a 20GB filesystem is arguably more serious than 85% utilization of a
10TB filesystem.

This uses check_mk's original alorithm to optionally adjust the
percentage thresholds based on size, using a "magic factor", a
"normalized size", and a "minium size to adjust".

The magic factor defaults to '1.0', which will not adjust thresholds.
The minimum size defaults to '100' (GB).  Filesystems smaller than this
will not be adapted.

check_mk's documentation has a lot more information on this, including
examples of adjustments based on the magic factor:
https://mathias-kettner.de/checkmk_filesystems.html

## [1.0.2] - 2015-08-04
### Changed
- general cleanup

## [1.0.1] - 2015-07-14
### Changed
- updated sensu-plugin gem to 1.2.0

##[1.0.0] - 2015-07-05
### Changed
- changed metrics filenames to conform to std
- updated Rakefile to remove cruft
- updated documentation links in README and CONTRIBUTING
- updated gemspec to put deps in alpha order

## [0.0.4] - 2015-06-22
### Fixed
- Correct check of inodes method on object fs_info which was always returning false

## [0.0.3] - 2015-06-02
### Fixed
- added binstubs

### Changed
- removed cruft from /lib

## [0.0.2] - 2015-04-21
### Fixed
- deployment issue

## [0.0.1] - 2015-04-21
### Added
- initial release

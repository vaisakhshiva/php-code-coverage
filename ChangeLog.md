# ChangeLog

All notable changes are documented in this file using the [Keep a CHANGELOG](http://keepachangelog.com/) principles.

## [10.0.0] - 2021-MM-DD

### Removed

* This component is no longer supported on PHP 7.3

## [9.2.6] - 2021-03-28

### Fixed

* [#846](https://github.com/sebastianbergmann/php-code-coverage/issues/846): Method name should not appear in the method signature attribute of Cobertura XML

## [9.2.5] - 2020-11-28

### Fixed

* [#831](https://github.com/sebastianbergmann/php-code-coverage/issues/831): Files that do not contain a newline are not handled correctly

## [9.2.4] - 2020-11-27

### Added

* [#834](https://github.com/sebastianbergmann/php-code-coverage/issues/834): Support `XDEBUG_MODE` environment variable

## [9.2.3] - 2020-10-30

### Changed

* Bumped required version of `nikic/php-parser`

## [9.2.2] - 2020-10-28

### Fixed

* [#820](https://github.com/sebastianbergmann/php-code-coverage/issues/820): Hidden dependency on PHPUnit

## [9.2.1] - 2020-10-26

### Fixed

* `SebastianBergmann\CodeCoverage\Exception` now correctly extends `\Throwable`

## [9.2.0] - 2020-10-02

### Added

* [#812](https://github.com/sebastianbergmann/php-code-coverage/pull/812): Support for Cobertura XML report format

### Changed

* Reduced the number of I/O operations performed by the static analysis cache

## [9.1.11] - 2020-09-19

### Fixed

* [#811](https://github.com/sebastianbergmann/php-code-coverage/issues/811): `T_FN` constant is used on PHP 7.3 where it is not available

## [9.1.10] - 2020-09-18

### Added

* `SebastianBergmann\CodeCoverage\Driver\Selector::forLineCoverage()` and `SebastianBergmann\CodeCoverage\Driver\Selector::forLineAndPathCoverage()` have been added

### Fixed

* [#810](https://github.com/sebastianbergmann/php-code-coverage/issues/810): `SebastianBergmann\CodeCoverage\Driver\Driver::forLineCoverage()` and `SebastianBergmann\CodeCoverage\Driver\Driver::forLineAndPathCoverage()` are marked as internal 

### Removed

* `SebastianBergmann\CodeCoverage\Driver\Driver::forLineCoverage()` and `SebastianBergmann\CodeCoverage\Driver\Driver::forLineAndPathCoverage()` are now deprecated

## [9.1.9] - 2020-09-15

### Fixed

* [#808](https://github.com/sebastianbergmann/php-code-coverage/issues/808): `PHP Warning: Use of undefined constant T_MATCH`

## [9.1.8] - 2020-09-07

### Changed

* [#800](https://github.com/sebastianbergmann/php-code-coverage/pull/800): All files on the inclusion list are no longer loaded when `SebastianBergmann\CodeCoverage::start()` is called for the first time and `processUncoveredFiles` is set to `true`

### Fixed

* [#799](https://github.com/sebastianbergmann/php-code-coverage/issues/799): Uncovered new line at end of file

## [9.1.7] - 2020-09-03

### Fixed

* Fixed regressions introduced in versions 9.1.5 and 9.1.6

## [9.1.6] - 2020-08-31

### Fixed

* [#799](https://github.com/sebastianbergmann/php-code-coverage/issues/799): Uncovered new line at end of file
* [#803](https://github.com/sebastianbergmann/php-code-coverage/issues/803): HTML report does not sort directories and files anymore

## [9.1.5] - 2020-08-27

### Changed

* [#800](https://github.com/sebastianbergmann/php-code-coverage/pull/800): All files on the inclusion list are no longer loaded when `SebastianBergmann\CodeCoverage::start()` is called for the first time and `processUncoveredFiles` is set to `true`

### Fixed

* [#797](https://github.com/sebastianbergmann/php-code-coverage/pull/797): Class name is wrongly removed from namespace name

## [9.1.4] - 2020-08-13

### Fixed

* [#793](https://github.com/sebastianbergmann/php-code-coverage/issues/793): Lines with `::class` constant are not covered

## [9.1.3] - 2020-08-10

### Changed

* Changed PHP-Parser usage to parse sourcecode according to the PHP version we are currently running on instead of using emulative lexing

## [9.1.2] - 2020-08-10

### Fixed

* [#791](https://github.com/sebastianbergmann/php-code-coverage/pull/791): Cache Warmer does not warm all caches

## [9.1.1] - 2020-08-10

### Added

* Added `SebastianBergmann\CodeCoverage::cacheDirectory()` method for querying where the cache writes its files

## [9.1.0] - 2020-08-10

### Added

* Implemented a persistent cache for information gathered using PHP-Parser based static analysis (hereinafter referred to as "cache")
* Added `SebastianBergmann\CodeCoverage::cacheStaticAnalysis(string $cacheDirectory)` method for enabling the cache; it will write its files to `$directory`
* Added `SebastianBergmann\CodeCoverage::doNotCacheStaticAnalysis` method for disabling the cache
* Added `SebastianBergmann\CodeCoverage::cachesStaticAnalysis()` method for querying whether the cache is enabled
* Added `SebastianBergmann\CodeCoverage\StaticAnalysis\CacheWarmer::warmCache()` method for warming the cache

## [9.0.0] - 2020-08-07

### Added

* [#761](https://github.com/sebastianbergmann/php-code-coverage/pull/761): Support for Branch Coverage and Path Coverage
* Added `SebastianBergmann\CodeCoverage\Driver\Driver::forLineCoverage()` for selecting the best available driver for line coverage
* Added `SebastianBergmann\CodeCoverage\Driver\Driver::forLineAndPathCoverage()` for selecting the best available driver for path coverage
* This component is now supported on PHP 8
* This component now supports Xdebug 3

### Changed

* [#746](https://github.com/sebastianbergmann/php-code-coverage/pull/746): Remove some ancient workarounds for very old Xdebug versions
* [#747](https://github.com/sebastianbergmann/php-code-coverage/pull/747): Use native filtering in PCOV and Xdebug drivers
* [#748](https://github.com/sebastianbergmann/php-code-coverage/pull/748): Store raw code coverage in value objects instead of arrays
* [#749](https://github.com/sebastianbergmann/php-code-coverage/pull/749): Store processed code coverage in value objects instead of arrays
* [#752](https://github.com/sebastianbergmann/php-code-coverage/pull/752): Rework how code coverage settings are propagated to the driver
* [#754](https://github.com/sebastianbergmann/php-code-coverage/pull/754): Implement collection of raw branch and path coverage
* [#755](https://github.com/sebastianbergmann/php-code-coverage/pull/755): Implement processing of raw branch and path coverage
* [#756](https://github.com/sebastianbergmann/php-code-coverage/pull/756): Improve handling of uncovered files
* `SebastianBergmann\CodeCoverage\Filter::addDirectoryToWhitelist()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::includeDirectory()`
* `SebastianBergmann\CodeCoverage\Filter::addFilesToWhitelist()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::includeFiles()`
* `SebastianBergmann\CodeCoverage\Filter::addFileToWhitelist()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::includeFile()`
* `SebastianBergmann\CodeCoverage\Filter::removeDirectoryFromWhitelist()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::excludeDirectory()`
* `SebastianBergmann\CodeCoverage\Filter::removeFileFromWhitelist()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::excludeFile()`
* `SebastianBergmann\CodeCoverage\Filter::isFiltered()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::isExcluded()`
* `SebastianBergmann\CodeCoverage\Filter::getWhitelist()` has been renamed to `SebastianBergmann\CodeCoverage\Filter::files()`
* The arguments for `CodeCoverage::__construct()` are no longer optional

### Fixed

* [#700](https://github.com/sebastianbergmann/php-code-coverage/pull/700): Throw an exception if code coverage fails to write to disk

### Removed

* `SebastianBergmann\CodeCoverage\CodeCoverage::setCacheTokens()` and `SebastianBergmann\CodeCoverage\CodeCoverage::getCacheTokens()` have been removed
* `SebastianBergmann\CodeCoverage\CodeCoverage::setCheckForUnintentionallyCoveredCode()` has been removed, please use `SebastianBergmann\CodeCoverage\CodeCoverage::enableCheckForUnintentionallyCoveredCode()` or `SebastianBergmann\CodeCoverage\CodeCoverage::disableCheckForUnintentionallyCoveredCode()` instead
* `SebastianBergmann\CodeCoverage\CodeCoverage::setSubclassesExcludedFromUnintentionallyCoveredCodeCheck()` has been removed, please use `SebastianBergmann\CodeCoverage\CodeCoverage::excludeSubclassesOfThisClassFromUnintentionallyCoveredCodeCheck()` instead
* `SebastianBergmann\CodeCoverage\CodeCoverage::setAddUncoveredFilesFromWhitelist()` has been removed, please use `SebastianBergmann\CodeCoverage\CodeCoverage::includeUncoveredFiles()` or `SebastianBergmann\CodeCoverage\CodeCoverage::excludeUncoveredFiles()` instead
* `SebastianBergmann\CodeCoverage\CodeCoverage::setProcessUncoveredFiles()` has been removed, please use `SebastianBergmann\CodeCoverage\CodeCoverage::processUncoveredFiles()` or `SebastianBergmann\CodeCoverage\CodeCoverage::doNotProcessUncoveredFiles()` instead
* `SebastianBergmann\CodeCoverage\CodeCoverage::setIgnoreDeprecatedCode()` has been removed, please use `SebastianBergmann\CodeCoverage\CodeCoverage::ignoreDeprecatedCode()` or `SebastianBergmann\CodeCoverage\CodeCoverage::doNotIgnoreDeprecatedCode()` instead
* `SebastianBergmann\CodeCoverage\CodeCoverage::setDisableIgnoredLines()` has been removed, please use `SebastianBergmann\CodeCoverage\CodeCoverage::enableAnnotationsForIgnoringCode()` or `SebastianBergmann\CodeCoverage\CodeCoverage::disableAnnotationsForIgnoringCode()` instead
* `SebastianBergmann\CodeCoverage\CodeCoverage::setCheckForMissingCoversAnnotation()` has been removed
* `SebastianBergmann\CodeCoverage\CodeCoverage::setCheckForUnexecutedCoveredCode()` has been removed
* `SebastianBergmann\CodeCoverage\CodeCoverage::setForceCoversAnnotation()` has been removed
* `SebastianBergmann\CodeCoverage\Filter::hasWhitelist()` has been removed, please use `SebastianBergmann\CodeCoverage\Filter::isEmpty()` instead
* `SebastianBergmann\CodeCoverage\Filter::getWhitelistedFiles()` has been removed
* `SebastianBergmann\CodeCoverage\Filter::setWhitelistedFiles()` has been removed

## [8.0.2] - 2020-05-23

### Fixed

* [#750](https://github.com/sebastianbergmann/php-code-coverage/pull/750): Inconsistent handling of namespaces
* [#751](https://github.com/sebastianbergmann/php-code-coverage/pull/751): Dead code is not highlighted correctly
* [#753](https://github.com/sebastianbergmann/php-code-coverage/issues/753): Do not use `$_SERVER['REQUEST_TIME']` because the test(ed) code might unset it

## [8.0.1] - 2020-02-19

### Fixed

* [#731](https://github.com/sebastianbergmann/php-code-coverage/pull/731): Confusing footer in the HTML report

## [8.0.0] - 2020-02-07

### Fixed

* [#721](https://github.com/sebastianbergmann/php-code-coverage/pull/721): Workaround for PHP bug [#79191](https://bugs.php.net/bug.php?id=79191)

### Removed

* This component is no longer supported on PHP 7.2

## [7.0.10] - 2019-11-20

### Fixed

* [#710](https://github.com/sebastianbergmann/php-code-coverage/pull/710): Code Coverage does not work in PhpStorm

## [7.0.9] - 2019-11-20

### Changed

* [#709](https://github.com/sebastianbergmann/php-code-coverage/pull/709): Prioritize PCOV over Xdebug

## [7.0.8] - 2019-09-17

### Changed

* Update HTML report Bootstrap 4.3.1, jQuery 3.4.1, and popper.js 1.15.0

## [7.0.7] - 2019-07-25

### Changed

* Bumped required version of php-token-stream

## [7.0.6] - 2019-07-08

### Changed

* Bumped required version of php-token-stream

## [7.0.5] - 2019-06-06

### Fixed

* [#681](https://github.com/sebastianbergmann/php-code-coverage/pull/681): `use function` statements are not ignored

## [7.0.4] - 2019-05-29

### Fixed

* [#682](https://github.com/sebastianbergmann/php-code-coverage/pull/682): Code that is not executed is reported as being executed when using PCOV

## [7.0.3] - 2019-02-26

### Fixed

* [#671](https://github.com/sebastianbergmann/php-code-coverage/issues/671): `TypeError` when directory name is a number

## [7.0.2] - 2019-02-15

### Changed

* Updated HTML report to Bootstrap 4.3.0

### Fixed

* [#667](https://github.com/sebastianbergmann/php-code-coverage/pull/667): `TypeError` in PHP reporter

## [7.0.1] - 2019-02-01

### Fixed

* [#664](https://github.com/sebastianbergmann/php-code-coverage/issues/664): `TypeError` when whitelisted file does not exist

## [7.0.0] - 2019-02-01

### Added

* [#663](https://github.com/sebastianbergmann/php-code-coverage/pull/663): Support for PCOV

### Fixed

* [#654](https://github.com/sebastianbergmann/php-code-coverage/issues/654): HTML report fails to load assets
* [#655](https://github.com/sebastianbergmann/php-code-coverage/issues/655): Popin pops in outside of screen

### Removed

* This component is no longer supported on PHP 7.1

## [6.1.4] - 2018-10-31

### Fixed

* [#650](https://github.com/sebastianbergmann/php-code-coverage/issues/650): Wasted screen space in HTML code coverage report

## [6.1.3] - 2018-10-23

### Changed

* Use `^3.1` of `sebastian/environment` again due to [regression](https://github.com/sebastianbergmann/environment/issues/31)

## [6.1.2] - 2018-10-23

### Fixed

* [#645](https://github.com/sebastianbergmann/php-code-coverage/pull/645): Crash that can occur when php-token-stream parses invalid files

## [6.1.1] - 2018-10-18

### Changed

* This component now allows `^4` of `sebastian/environment`

## [6.1.0] - 2018-10-16

### Changed

* Class names are now abbreviated (unqualified name shown, fully qualified name shown on hover) in the file view of the HTML report
* Update HTML report to Bootstrap 4

[10.0.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2...master
[9.2.6]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2.5...9.2
[9.2.5]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2.4...9.2.5
[9.2.4]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2.3...9.2.4
[9.2.3]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2.2...9.2.3
[9.2.2]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2.1...9.2.2
[9.2.1]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.2.0...9.2.1
[9.2.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.11...9.2.0
[9.1.11]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.10...9.1.11
[9.1.10]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.9...9.1.10
[9.1.9]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.8...9.1.9
[9.1.8]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.7...9.1.8
[9.1.7]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.6...9.1.7
[9.1.6]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.5...9.1.6
[9.1.5]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.4...9.1.5
[9.1.4]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.3...9.1.4
[9.1.3]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.2...9.1.3
[9.1.2]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.1...9.1.2
[9.1.1]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.1.0...9.1.1
[9.1.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/9.0.0...9.1.0
[9.0.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/8.0...9.0.0
[8.0.2]: https://github.com/sebastianbergmann/php-code-coverage/compare/8.0.1...8.0.2
[8.0.1]: https://github.com/sebastianbergmann/php-code-coverage/compare/8.0.0...8.0.1
[8.0.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.10...8.0.0
[7.0.10]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.9...7.0.10
[7.0.9]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.8...7.0.9
[7.0.8]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.7...7.0.8
[7.0.7]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.6...7.0.7
[7.0.6]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.5...7.0.6
[7.0.5]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.4...7.0.5
[7.0.4]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.3...7.0.4
[7.0.3]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.2...7.0.3
[7.0.2]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.1...7.0.2
[7.0.1]: https://github.com/sebastianbergmann/php-code-coverage/compare/7.0.0...7.0.1
[7.0.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/6.1.4...7.0.0
[6.1.4]: https://github.com/sebastianbergmann/php-code-coverage/compare/6.1.3...6.1.4
[6.1.3]: https://github.com/sebastianbergmann/php-code-coverage/compare/6.1.2...6.1.3
[6.1.2]: https://github.com/sebastianbergmann/php-code-coverage/compare/6.1.1...6.1.2
[6.1.1]: https://github.com/sebastianbergmann/php-code-coverage/compare/6.1.0...6.1.1
[6.1.0]: https://github.com/sebastianbergmann/php-code-coverage/compare/6.0...6.1.0


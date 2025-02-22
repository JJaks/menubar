# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

### [10.0.1](https://github.com/JJaks/menubar/compare/v10.0.0...v10.0.1) (2023-04-17)

## 10.0.0 (2023-04-17)


### ⚠ BREAKING CHANGES

* Please use Electron 9 with this menubar version.
* Menubar's recommended peer dependency is `electron@^8.0.0`
* - Drop support for Electron 4, 5, and 6.
- Remove deprecated passing string argument to `menubar`, use `dir` field instead
```diff
- menubar('/home/me/MY_ABSOLUTE_PATH');
+ menubar({ dir: '/home/me/MY_ABSOLUTE_PATH' });
```
- Remove deprecated passing `x`, `y`, `height`, `width`, `alwaysOnTop` fields to `menubar`, pass them instead into the `browserWindow` field
```diff
- menubar({
-   x: 12,
-   y: 34,
-   height: 500,
-   width: 320,
-   alwaysOnTop: true
- });
+ menubar({
+   browserWindow: {
+     x: 12,
+     y: 34,
+     height: 500,
+     width: 320,
+     alwaysOnTop: true
+  }
+ });
```
* We're using a named export in Typescript now:
```diff
- var menubar = require('menubar');
+ var { menubar } = require('menubar');
```

Alternatively, using ES6/TS syntax:
```javascript
import { menubar } from 'menubar';
```

### Features

* add `before-load` event ([#370](https://github.com/maxogden/menubar/issues/370)) ([3247986](https://github.com/maxogden/menubar/commit/3247986f164d8b2fb2912ab33beb25c9c6d8ece3))
* Add `browserWindow` field in options, deprecate `height`, `width`, `x`, `y`, `alwaysOnTop` in favor of `browserWindow` ([#18](https://github.com/maxogden/menubar/issues/18)) ([0b2d897](https://github.com/maxogden/menubar/commit/0b2d8979ba21eebb58312690426be30b6cf4a247))
* Add Electron 20 as a peerDependency ([#379](https://github.com/maxogden/menubar/issues/379)) ([4c027b2](https://github.com/maxogden/menubar/commit/4c027b22499c7c83a4d87b9aa17d5e86f3172b68))
* add electron 22 support ([#414](https://github.com/maxogden/menubar/issues/414)) ([a39382f](https://github.com/maxogden/menubar/commit/a39382fe843953395bf99267ee83102def70b06e))
* add option activateWithApp to allow not activate with this event ([#361](https://github.com/maxogden/menubar/issues/361)) ([8384bf2](https://github.com/maxogden/menubar/commit/8384bf24abe6138aded26fcd7bd6d1d7a325f319))
* Adding a loadUrlOptions option ([#263](https://github.com/maxogden/menubar/issues/263)) ([8e6bd01](https://github.com/maxogden/menubar/commit/8e6bd0154aaee02a5d601bbe37c51c55065c3923))
* Allow skipping loadUrl ([#257](https://github.com/maxogden/menubar/issues/257)) ([095486a](https://github.com/maxogden/menubar/commit/095486ab338df26fc4d6a1e7a658cfa9fa4a69b7))
* electron 21 support ([#382](https://github.com/maxogden/menubar/issues/382)) ([c9d5b61](https://github.com/maxogden/menubar/commit/c9d5b61da2b55e20e9b2d0f4c0181c57f33a27c3))
* Support Electron 7 ([#250](https://github.com/maxogden/menubar/issues/250)) ([b54dce5](https://github.com/maxogden/menubar/commit/b54dce58faec17b95c24faeae77cbc264b0168d0))
* Support Electron 8 ([#268](https://github.com/maxogden/menubar/issues/268)) ([ad99c5a](https://github.com/maxogden/menubar/commit/ad99c5add02ab6d0d751cf6bda8a2c96c674620f))
* Support Electron 9 ([#286](https://github.com/maxogden/menubar/issues/286)) ([44cf1b1](https://github.com/maxogden/menubar/commit/44cf1b1e6cce83f9e63a39f1d32fbb664396e7bc))
* Support Electron.NativeImage icon argument ([#7](https://github.com/maxogden/menubar/issues/7)) ([03d67f3](https://github.com/maxogden/menubar/commit/03d67f3fd572ed2305b5b71ed53f28c2de2b3851))


### Bug Fixes

* Add electron 16 support ([#364](https://github.com/maxogden/menubar/issues/364)) ([325e151](https://github.com/maxogden/menubar/commit/325e1517cfc407bc0ccc98be776d8d9590d6f119))
* Add electron 17 support ([#373](https://github.com/maxogden/menubar/issues/373)) ([fafc29f](https://github.com/maxogden/menubar/commit/fafc29f168e91369ad5d60a61abc0363076c303a))
* Add support for Electron 10 and 11 ([#321](https://github.com/maxogden/menubar/issues/321)) ([4a89656](https://github.com/maxogden/menubar/commit/4a8965628a0a1a7a14602fef3add7bef436a508f))
* Add support for Electron 12 ([#332](https://github.com/maxogden/menubar/issues/332)) ([c1f055d](https://github.com/maxogden/menubar/commit/c1f055daed76be2d0f408fda5d4835defcd59dcc))
* Add support for Electron 13 ([#347](https://github.com/maxogden/menubar/issues/347)) ([fbf07bd](https://github.com/maxogden/menubar/commit/fbf07bd0bd24b2aac26cdd1db61eb55924f3ee63))
* Add support for electron 14 and 15 ([#358](https://github.com/maxogden/menubar/issues/358)) ([8eaba8c](https://github.com/maxogden/menubar/commit/8eaba8cdfcd3ce9427ee3ffd65b3426c62f65048))
* Add support for electron 19 ([#376](https://github.com/maxogden/menubar/issues/376)) ([6d0feb0](https://github.com/maxogden/menubar/commit/6d0feb0e492681200966dde10a63a73cfb503138))
* arrow example problem ([#342](https://github.com/maxogden/menubar/issues/342)) ([64b80d5](https://github.com/maxogden/menubar/commit/64b80d5f49ebb367b75e21e88af15fdc874cda86))
* calling showWindow() prevents menubar window from closing ([#287](https://github.com/maxogden/menubar/issues/287)) ([53d8f82](https://github.com/maxogden/menubar/commit/53d8f82b604ad5555f59108a97234ebf32e43f80))
* Correct position on Windows & multi-taskbar ([#217](https://github.com/maxogden/menubar/issues/217)) ([4f29fe2](https://github.com/maxogden/menubar/commit/4f29fe2a26e61f91d62f29e384e1da4840fb0966)), closes [#196](https://github.com/maxogden/menubar/issues/196)
* **deps:** [Security] bump acorn from 6.1.1 to 6.4.1 ([#272](https://github.com/maxogden/menubar/issues/272)) ([1332b77](https://github.com/maxogden/menubar/commit/1332b774372de69c04e2a098833ae35775c35cad))
* Fix accessing Menubar.window ([#214](https://github.com/maxogden/menubar/issues/214)) ([cd5ef73](https://github.com/maxogden/menubar/commit/cd5ef73cf7f1e740429a8c84040adbab2545aa05))
* Fix changelog links ([#204](https://github.com/maxogden/menubar/issues/204)) ([de96756](https://github.com/maxogden/menubar/commit/de96756c20cd441c264a9ab141c4906498649479))
* Fix crash on windows position ([#235](https://github.com/maxogden/menubar/issues/235)) ([cbbe175](https://github.com/maxogden/menubar/commit/cbbe1753fb2f24a211311ad79e21dc20435e3a79))
* Fix double 'after-hide' event ([#216](https://github.com/maxogden/menubar/issues/216)) ([a4d900e](https://github.com/maxogden/menubar/commit/a4d900eb3e51ec02124755e2d56b71d261ddec2e))
* Improve 'windows' OS detection of taskbar location ([#307](https://github.com/maxogden/menubar/issues/307)) ([4726584](https://github.com/maxogden/menubar/commit/4726584664148a57656c40872836ebba2d030980))
* Remove postinstall, export taskbarLocation ([#226](https://github.com/maxogden/menubar/issues/226)) ([941b3be](https://github.com/maxogden/menubar/commit/941b3bed76b2dcf46ef20d9ae77d00ff35f6eff6))
* Show window on dock icon click ([#279](https://github.com/maxogden/menubar/issues/279)) ([a8607fa](https://github.com/maxogden/menubar/commit/a8607fa708d229d9124471127482fe461198f1f3))
* Support Electron 6 ([#242](https://github.com/maxogden/menubar/issues/242)) ([1fd9bd7](https://github.com/maxogden/menubar/commit/1fd9bd7f1c63f13b286702ed0839e429770446f1))
* update prevent flicker on Windows (fixes [#274](https://github.com/maxogden/menubar/issues/274)) ([#276](https://github.com/maxogden/menubar/issues/276)) ([9592f34](https://github.com/maxogden/menubar/commit/9592f3437ce3660b6464f5b436ed111291eb75d3))
* Update to Electron 5 ([#15](https://github.com/maxogden/menubar/issues/15)) ([ce86216](https://github.com/maxogden/menubar/commit/ce86216ba73d9ed9267415609e98aa72ddd1bdd8))
* Use cat icon if no icon provided ([#205](https://github.com/maxogden/menubar/issues/205)) ([fc02e02](https://github.com/maxogden/menubar/commit/fc02e024571f249961d7b43e6df27dfec47630b2))
* Window does not show when already app is ready ([#8](https://github.com/maxogden/menubar/issues/8)) ([251fb21](https://github.com/maxogden/menubar/commit/251fb21de85b3a78dc564a08248e5a4f84a21d71))
* window position on linux & windows when taskbar is on the left ([#343](https://github.com/maxogden/menubar/issues/343)) ([5d8e0c8](https://github.com/maxogden/menubar/commit/5d8e0c89996f67b58f059ec767a87db104a90292))


* Convert all codebase to typescript ([#2](https://github.com/maxogden/menubar/issues/2)) ([820d41a](https://github.com/maxogden/menubar/commit/820d41a77bcdbdfc90bdeee8139a48b6f5803297))

## [9.3.0](https://github.com/maxogden/menubar/compare/v9.2.3...v9.3.0) (2023-02-13)


### Features

* add electron 22 support ([#414](https://github.com/maxogden/menubar/issues/414)) ([a39382f](https://github.com/maxogden/menubar/commit/a39382fe843953395bf99267ee83102def70b06e))

### [9.2.3](https://github.com/maxogden/menubar/compare/v9.2.2...v9.2.3) (2022-10-05)


### Features

* electron 21 support ([#382](https://github.com/maxogden/menubar/issues/382)) ([c9d5b61](https://github.com/maxogden/menubar/commit/c9d5b61da2b55e20e9b2d0f4c0181c57f33a27c3))

### [9.2.2](https://github.com/maxogden/menubar/compare/v9.2.1...v9.2.2) (2022-09-05)


### Features

* Add Electron 20 as a peerDependency ([#379](https://github.com/maxogden/menubar/issues/379)) ([4c027b2](https://github.com/maxogden/menubar/commit/4c027b22499c7c83a4d87b9aa17d5e86f3172b68))


### Bug Fixes

* arrow example problem ([#342](https://github.com/maxogden/menubar/issues/342)) ([64b80d5](https://github.com/maxogden/menubar/commit/64b80d5f49ebb367b75e21e88af15fdc874cda86))

### [9.2.1](https://github.com/maxogden/menubar/compare/v9.2.0...v9.2.1) (2022-07-11)


### Bug Fixes

* Add support for electron 19 ([#376](https://github.com/maxogden/menubar/issues/376)) ([6d0feb0](https://github.com/maxogden/menubar/commit/6d0feb0e492681200966dde10a63a73cfb503138))

## [9.2.0](https://github.com/maxogden/menubar/compare/v9.1.2...v9.2.0) (2022-04-11)


### Features

* add `before-load` event ([#370](https://github.com/maxogden/menubar/issues/370)) ([3247986](https://github.com/maxogden/menubar/commit/3247986f164d8b2fb2912ab33beb25c9c6d8ece3))

### [9.1.2](https://github.com/maxogden/menubar/compare/v9.1.1...v9.1.2) (2022-03-29)


### Bug Fixes

* Add electron 17 support ([#373](https://github.com/maxogden/menubar/issues/373)) ([fafc29f](https://github.com/maxogden/menubar/commit/fafc29f168e91369ad5d60a61abc0363076c303a))

### [9.1.1](https://github.com/maxogden/menubar/compare/v9.1.0...v9.1.1) (2021-12-09)


### Bug Fixes

* Add electron 16 support ([#364](https://github.com/maxogden/menubar/issues/364)) ([325e151](https://github.com/maxogden/menubar/commit/325e1517cfc407bc0ccc98be776d8d9590d6f119))

## [9.1.0](https://github.com/maxogden/menubar/compare/v9.0.6...v9.1.0) (2021-10-27)


### Features

* add option activateWithApp to allow not activate with this event ([#361](https://github.com/maxogden/menubar/issues/361)) ([8384bf2](https://github.com/maxogden/menubar/commit/8384bf24abe6138aded26fcd7bd6d1d7a325f319))

### [9.0.6](https://github.com/maxogden/menubar/compare/v9.0.5...v9.0.6) (2021-10-15)


### Bug Fixes

* Add support for electron 14 and 15 ([#358](https://github.com/maxogden/menubar/issues/358)) ([8eaba8c](https://github.com/maxogden/menubar/commit/8eaba8cdfcd3ce9427ee3ffd65b3426c62f65048))

### [9.0.5](https://github.com/maxogden/menubar/compare/v9.0.4...v9.0.5) (2021-06-28)


### Bug Fixes

* Add support for Electron 13 ([#347](https://github.com/maxogden/menubar/issues/347)) ([fbf07bd](https://github.com/maxogden/menubar/commit/fbf07bd0bd24b2aac26cdd1db61eb55924f3ee63))
* window position on linux & windows when taskbar is on the left ([#343](https://github.com/maxogden/menubar/issues/343)) ([5d8e0c8](https://github.com/maxogden/menubar/commit/5d8e0c89996f67b58f059ec767a87db104a90292))

### [9.0.4](https://github.com/maxogden/menubar/compare/v9.0.3...v9.0.4) (2021-05-03)


### Bug Fixes

* Add support for Electron 12 ([#332](https://github.com/maxogden/menubar/issues/332)) ([c1f055d](https://github.com/maxogden/menubar/commit/c1f055daed76be2d0f408fda5d4835defcd59dcc))

### [9.0.3](https://github.com/maxogden/menubar/compare/v9.0.2...v9.0.3) (2021-02-24)


### Bug Fixes

* Add support for Electron 10 and 11 ([#321](https://github.com/maxogden/menubar/issues/321)) ([4a89656](https://github.com/maxogden/menubar/commit/4a8965628a0a1a7a14602fef3add7bef436a508f))

### [9.0.2](https://github.com/maxogden/menubar/compare/v9.0.1...v9.0.2) (2021-01-20)


### Bug Fixes

* Improve 'windows' OS detection of taskbar location ([#307](https://github.com/maxogden/menubar/issues/307)) ([4726584](https://github.com/maxogden/menubar/commit/4726584664148a57656c40872836ebba2d030980))

### [9.0.1](https://github.com/maxogden/menubar/compare/v9.0.0...v9.0.1) (2020-05-28)


### Bug Fixes

* calling showWindow() prevents menubar window from closing ([#287](https://github.com/maxogden/menubar/issues/287)) ([53d8f82](https://github.com/maxogden/menubar/commit/53d8f82b604ad5555f59108a97234ebf32e43f80))

## [9.0.0](https://github.com/maxogden/menubar/compare/v8.0.2...v9.0.0) (2020-05-27)


### ⚠ BREAKING CHANGES

* Please use Electron 9 with this menubar version.

### Features

* Support Electron 9 ([#286](https://github.com/maxogden/menubar/issues/286)) ([44cf1b1](https://github.com/maxogden/menubar/commit/44cf1b1e6cce83f9e63a39f1d32fbb664396e7bc))

### [8.0.2](https://github.com/maxogden/menubar/compare/v8.0.1...v8.0.2) (2020-04-27)


### Bug Fixes

* Show window on dock icon click ([#279](https://github.com/maxogden/menubar/issues/279)) ([a8607fa](https://github.com/maxogden/menubar/commit/a8607fa708d229d9124471127482fe461198f1f3))
* update prevent flicker on Windows (fixes [#274](https://github.com/maxogden/menubar/issues/274)) ([#276](https://github.com/maxogden/menubar/issues/276)) ([9592f34](https://github.com/maxogden/menubar/commit/9592f3437ce3660b6464f5b436ed111291eb75d3))

### [8.0.1](https://github.com/maxogden/menubar/compare/v8.0.0...v8.0.1) (2020-03-14)


### Bug Fixes

* **deps:** [Security] bump acorn from 6.1.1 to 6.4.1 ([#272](https://github.com/maxogden/menubar/issues/272)) ([1332b77](https://github.com/maxogden/menubar/commit/1332b774372de69c04e2a098833ae35775c35cad))

## [8.0.0](https://github.com/maxogden/menubar/compare/v7.2.0...v8.0.0) (2020-02-10)


### ⚠ BREAKING CHANGES

* Menubar's recommended peer dependency is `electron@^8.0.0`

### Features

* Support Electron 8 ([#268](https://github.com/maxogden/menubar/issues/268)) ([ad99c5a](https://github.com/maxogden/menubar/commit/ad99c5add02ab6d0d751cf6bda8a2c96c674620f))

## [7.2.0](https://github.com/maxogden/menubar/compare/v7.1.0...v7.2.0) (2020-01-16)


### Features

* Adding a loadUrlOptions option ([#263](https://github.com/maxogden/menubar/issues/263)) ([8e6bd01](https://github.com/maxogden/menubar/commit/8e6bd0154aaee02a5d601bbe37c51c55065c3923))

## [7.1.0](https://github.com/maxogden/menubar/compare/v7.0.0...v7.1.0) (2019-11-25)


### Features

* Allow skipping loadUrl ([#257](https://github.com/maxogden/menubar/issues/257)) ([095486a](https://github.com/maxogden/menubar/commit/095486ab338df26fc4d6a1e7a658cfa9fa4a69b7))

# [7.0.0](https://github.com/maxogden/menubar/compare/v6.0.8...v7.0.0) (2019-10-23)


* feat!: Support Electron 7 (#250) ([b54dce5](https://github.com/maxogden/menubar/commit/b54dce5)), closes [#250](https://github.com/maxogden/menubar/issues/250)


### BREAKING CHANGES

* - Drop support for Electron 4, 5, and 6.
- Remove deprecated passing string argument to `menubar`, use `dir` field instead
```diff
- menubar('/home/me/MY_ABSOLUTE_PATH');
+ menubar({ dir: '/home/me/MY_ABSOLUTE_PATH' });
```
- Remove deprecated passing `x`, `y`, `height`, `width`, `alwaysOnTop` fields to `menubar`, pass them instead into the `browserWindow` field
```diff
- menubar({
-   x: 12,
-   y: 34,
-   height: 500,
-   width: 320,
-   alwaysOnTop: true
- });
+ menubar({
+   browserWindow: {
+     x: 12,
+     y: 34,
+     height: 500,
+     width: 320,
+     alwaysOnTop: true
+  }
+ });
```



## [6.0.8](https://github.com/maxogden/menubar/compare/v6.0.7...v6.0.8) (2019-09-16)


### Bug Fixes

* Move doc tool to `devDependencies` ([#245](https://github.com/maxogden/menubar/issues/245)) ([2756c7a](https://github.com/maxogden/menubar/commit/2756c7a))



## [6.0.7](https://github.com/maxogden/menubar/compare/v6.0.6...v6.0.7) (2019-07-31)


### Bug Fixes

* Support Electron 6 ([#242](https://github.com/maxogden/menubar/issues/242)) ([1fd9bd7](https://github.com/maxogden/menubar/commit/1fd9bd7))



## [6.0.6](https://github.com/maxogden/menubar/compare/v6.0.5...v6.0.6) (2019-07-02)


### Bug Fixes

* Fix crash on windows position ([#235](https://github.com/maxogden/menubar/issues/235)) ([cbbe175](https://github.com/maxogden/menubar/commit/cbbe175))



## [6.0.5](https://github.com/maxogden/menubar/compare/v6.0.4...v6.0.5) (2019-06-11)


### Bug Fixes

* Remove postinstall, export taskbarLocation ([#226](https://github.com/maxogden/menubar/issues/226)) ([941b3be](https://github.com/maxogden/menubar/commit/941b3be))



## [6.0.4](https://github.com/maxogden/menubar/compare/v6.0.3...v6.0.4) (2019-06-11)


### Bug Fixes

* Correct position on Windows & multi-taskbar ([#217](https://github.com/maxogden/menubar/issues/217)) ([4f29fe2](https://github.com/maxogden/menubar/commit/4f29fe2)), closes [#196](https://github.com/maxogden/menubar/issues/196)
* Fix double 'after-hide' event ([#216](https://github.com/maxogden/menubar/issues/216)) ([a4d900e](https://github.com/maxogden/menubar/commit/a4d900e))



## [6.0.3](https://github.com/maxogden/menubar/compare/v6.0.2...v6.0.3) (2019-06-05)


### Bug Fixes

* Fix accessing Menubar.window ([#214](https://github.com/maxogden/menubar/issues/214)) ([cd5ef73](https://github.com/maxogden/menubar/commit/cd5ef73))



## [6.0.2](https://github.com/maxogden/menubar/compare/v6.0.1...v6.0.2) (2019-05-31)


### Bug Fixes

* Use cat icon if no icon provided ([#205](https://github.com/maxogden/menubar/issues/205)) ([fc02e02](https://github.com/maxogden/menubar/commit/fc02e02))



## [6.0.1](https://github.com/maxogden/menubar/compare/v6.0.0...v6.0.1) (2019-05-31)


### Bug Fixes

* Fix changelog links ([#204](https://github.com/maxogden/menubar/issues/204)) ([de96756](https://github.com/maxogden/menubar/commit/de96756))



# [6.0.0](https://github.com/maxogden/menubar/compare/v5.2.3...v6.0.0) (2019-05-31)


### Bug Fixes

* Update to Electron 5 ([#15](https://github.com/amaurym/g/menubar/issues/15)) ([ce86216](https://github.com/maxogden/menubar/commit/ce86216))
* Window does not show when already app is ready ([#8](https://github.com/amaurym/g/menubar/issues/8)) ([251fb21](https://github.com/maxogden/menubar/commit/251fb21))


### Code Refactoring

* Convert all codebase to typescript ([#2](https://github.com/amaurym/g/menubar/issues/2)) ([820d41a](https://github.com/maxogden/menubar/commit/820d41a))


### Features

* Add `browserWindow` field in options, deprecate `height`, `width`, `x`, `y`, `alwaysOnTop` in favor of `browserWindow` ([#18](https://github.com/amaurym/g/menubar/issues/18)) ([0b2d897](https://github.com/maxogden/menubar/commit/0b2d897))
* Support Electron.NativeImage icon argument ([#7](https://github.com/amaurym/g/menubar/issues/7)) ([03d67f3](https://github.com/maxogden/menubar/commit/03d67f3))


### BREAKING CHANGES

* We're using a named export in Typescript now:
```diff
- var menubar = require('menubar');
+ var { menubar } = require('menubar');
```

Alternatively, using ES6/TS syntax:
```javascript
import { menubar } from 'menubar';
```

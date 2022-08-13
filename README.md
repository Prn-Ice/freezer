<!-- TOC -->

- [1. Guide 🌎](#1-guide-)
  - [1.1. Motivation 💎](#11-motivation-)
  - [1.2. Getting Started 🏄](#12-getting-started-)
    - [1.2.1. Prerequisite](#121-prerequisite)
    - [1.2.2. Install Library](#122-install-library)
    - [1.2.3. Create a JSON File](#123-create-a-json-file)
    - [1.2.4. Execute Command](#124-execute-command)
  - [1.3. Contribution 🏆](#13-contribution-)
  - [1.4. Support ❤️](#14-support-️)
  - [1.5. License 🔑](#15-license-)
  - [1.6. More Information 🧐](#16-more-information-)

<!-- /TOC -->

# 1. Guide 🌎

This library was built on the foundation of the [json_serializable](https://pub.dev/packages/json_serializable) and [freezed](https://pub.dev/packages/freezed) libraries.

This library provides the ability to automatically generate class objects supported by the [freezed](https://pub.dev/packages/freezed) library **directly from JSON files**.

Show some ❤️ and star the repo to support the project.

## 1.1. Motivation 💎

- JSON-based model design.
- Synchronize the design and implementation of model objects.
- Expand the possibilities of the freezed library even more.

## 1.2. Getting Started 🏄

### 1.2.1. Prerequisite

The codes automatically generated by this library depend on [json_serializable](https://pub.dev/packages/json_serializable) and [freezed](https://pub.dev/packages/freezed).

So, let's add the prerequisite libraries to `pubspec.yaml` as follows.

```yaml
dependencies:
  json_annotation: ^4.6.0
  freezed_annotation: ^2.1.0

dev_dependencies:
  json_serializable: ^6.3.1
  freezed: ^2.1.0+1
```

### 1.2.2. Install Library

Next, let's install the libraries to use the **freezer** functionality.

**With Dart:**

```bash
dart pub get freezer
```

**With Flutter:**

```bash
flutter pub get freezer
```

### 1.2.3. Create a JSON File

**freezer** interprets JSON files as design information and automatically generates object classes supported by the [freezed](https://pub.dev/packages/freezed) library.

And you need to note following rules when you use the `freezer`.

1. **freezer** parses files with the `.freezer.json` extension.
2. **freezer** parses JSON files stored in the `.design` folder.

So, now let's create a JSON file with the following structure as a trial.

```json
{
  "shop": {
    "name.!required": "My Fancy Shop",
    "product": [
      {
        "name": "Chocolate",
        "price": 5.99
      },
      {
        "name": "Gummy",
        "price": 8.99
      }
    ],
    "closed": false
  }
}
```

And then store this JSON file in the `.design` folder of the root of project.

```bash
.
├── analysis_options.yaml
├── design
│   └── shop.freezer.json
├── lib
├── pubspec.lock
└── pubspec.yaml
```

### 1.2.4. Execute Command

Now let's execute the following command and see what happens!

```bash
dart pub run freezer:main
```

Then, this trial is successful if the following output is obtained.

```bash
Started process for 1 files

[INFO] Reading cached asset graph completed, took 31ms
[INFO] Checking for updates since last build completed, took 293ms
[INFO] Running build completed, took 917ms
[INFO] Caching finalized dependency graph completed, took 17ms
[INFO] Succeeded after 939ms with 4 outputs (4 actions)

┏━━ Generated dart files
┣ ✔ /Users/user/package/lib//product.dart
┣ ✔ /Users/user/package/lib//product.freezed.dart
┣ ✔ /Users/user/package/lib//product.g.dart
┣ ✔ /Users/user/package/lib//shop.dart
┣ ✔ /Users/user/package/lib//shop.freezed.dart
┣ ✔ /Users/user/package/lib//shop.g.dart
┗━━ 6 files in 1.1904 seconds
```

And you can see generated dart codes in the `.lib` folder like below.

```bash
.
├── analysis_options.yaml
├── design
│   └── shop.freezer.json
├── lib
│   ├── product.dart
│   ├── product.freezed.dart
│   ├── product.g.dart
│   ├── shop.dart
│   ├── shop.freezed.dart
│   └── shop.g.dart
├── pubspec.lock
└── pubspec.yaml
```

## 1.3. Contribution 🏆

If you would like to contribute to **freezer**, please create an [issue](https://github.com/myConsciousness/freezer/issues) or create a Pull Request.

There are many ways to contribute to the OSS. For example, the following subjects can be considered:

- There are request parameters or response fields that are not implemented.
- Documentation is outdated or incomplete.
- Have a better way or idea to achieve the functionality.
- etc...

You can see more details from resources below:

- [Contributor Covenant Code of Conduct](https://github.com/myConsciousness/freezer/blob/main/CODE_OF_CONDUCT.md)
- [Contribution Guidelines](https://github.com/myConsciousness/freezer/blob/main/CONTRIBUTING.md)
- [Style Guide](https://github.com/myConsciousness/freezer/blob/main/STYLEGUIDE.md)

Or you can create a [discussion](https://github.com/myConsciousness/freezer/discussions) if you like.

**Feel free to join this development, diverse opinions make software better!**

## 1.4. Support ❤️

The simplest way to show us your support is by **giving the project a star** at [GitHub](https://github.com/myConsciousness/freezer) and [Pub.dev](https://pub.dev/packages/freezer).

You can also support this project by **becoming a sponsor** on GitHub:

## 1.5. License 🔑

All resources of **freezer** is provided under the `BSD-3` license.

```license
Copyright 2022 Kato Shinya. All rights reserved.
Redistribution and use in source and binary forms, with or without
modification, are permitted provided the conditions.
```

> **Note**</br>
> License notices in the source are strictly validated based on `.github/header-checker-lint.yml`. Please check [header-checker-lint.yml](https://github.com/myConsciousness/freezer/tree/main/.github/header-checker-lint.yml) for the permitted standards.

## 1.6. More Information 🧐

**freezer** was designed and implemented by **_Kato Shinya ([@myConsciousness](https://github.com/myConsciousness))_**.

- [Creator Profile](https://github.com/myConsciousness)
- [License](https://github.com/myConsciousness/freezer/blob/main/LICENSE)
- [API Document](https://pub.dev/documentation/freezer/latest/freezer/freezer-library.html)
- [Release Note](https://github.com/myConsciousness/freezer/releases)
- [Bug Report](https://github.com/myConsciousness/freezer/issues)

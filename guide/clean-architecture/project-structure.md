# Folder structure

## Overview

In this template, we've tried to follow the [clean architecture](./) best practices when it comes to organizing files and directories within the project

We are not going to focus on the layout conventions made by Flutter (You can find more details [here](https://dart.dev/tools/pub/package-layout)), but we are going to explain the organization choices under the root folder `lib` , and the role of each directory.

![](<../../.gitbook/assets/Capture13 (1).PNG>)

As you can see in the image above, under the `lib` folder, there are two main directories :

* **`src`**: contains the source code files and logic implementation (it is private).
* **`public`** : exports API from several files in `lib/src`, to expose a public API that can be used within other libraries (or [packages](https://dart.dev/guides/libraries/create-library-packages)).

## Organizing the code

Under the source folder (`lib/src`), we followed the clean architecture guidelines and organize the code into two main directories:&#x20;

### Core

This folder includes a set of classes, functions and mini libraries that enable to configure the app and make the code structure more efficient by enabling some functionalities such as notifications, authentication, theming, …, etc.

The `core` folder is splitted into multiple subfolders, following the role of each folder:

* **common**: contains commonly used base classes, helpers, utils functions and some shared widgets.
* **database**: **** configure app database
* **di**: configure dependency injection
* **localization**: configure supported locales, default language and  app language class
* **navigation:** configure routing in the app
* **storage:** configure storage (local storage)
* **theme**: configure theme variables (colors, fonts, spacing,...etc.)



### Features

The features include all the domain related features, where each folder under `lib/features`, holds a single feature and each one is divided into three layers:&#x20;

![](<../../.gitbook/assets/Capture14 (2).PNG>)

#### Domain

The domain layer includes the domain related classes : **entities**, **repositories** (interfaces) and **usescases** implementations.

#### Data

The data layer includes the data related classes: data **models**, **repositories** (implementations) **** and data sources (services) implementation logic.

#### Presentation

The presentation layer includes the presentation related components, grouped into **pages** for main screens and **widgets** for reusable widgets and also **blocs** (business logic components) that manage the state of the widgets and handle user experience related events (Read more on [Bloc State Management](https://bloclibrary.dev)).

**Note:** The file `main.dart` in each directory is the entry point, and it is responsible for initializing the feature by registering necessary services, repositories and blocs into DI container.

{% hint style="info" %}
To have advanced look and see more details on each component (class, functions,...etc.) visit the application [API references](https://www.example.com).
{% endhint %}

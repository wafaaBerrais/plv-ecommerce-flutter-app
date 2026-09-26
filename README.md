# PLV: E-commerce Mobile App (Flutter)

Cross-platform **Flutter** mobile app for an online shop selling **custom advertising flags and promotional displays** (PLV, *publicité sur le lieu de vente*). Customers browse the catalogue, manage their account, and place and track orders through a multi-step checkout connected to the shop's REST API.

> 💼 **Freelance mission, June–August 2024.** Front-end mobile developer in a team of two, with [Merouane Mezouari (@RMRdev28)](https://github.com/RMRdev28).
> This repository is a fork of the team repository [RMRdev28/app-mobile](https://github.com/RMRdev28/app-mobile), where the work was done through feature branches and pull requests.

---

## Features

- **Catalogue:** home page with image carousels, shop page with product categories, product cards (horizontal and vertical), details, ratings and "read more" descriptions.
- **Authentication:** sign-up, log-in, forgotten password; token-based authentication with secure storage and a route guard for protected pages.
- **User profile:** profile page, profile update (with wilaya/commune selection for Algerian addresses), order history ("my purchases") and order details.
- **Checkout:** cart, delivery information, payment and order confirmation in a **4-step order flow**.
- **Push notifications** with Firebase.

## My contributions

I built most of the user-facing screens: **11 merged pull requests** and 29 of the 39 commits.

| Pull request | Feature |
|---|---|
| [#5](https://github.com/RMRdev28/app-mobile/pull/5) | Profile screen |
| [#7](https://github.com/RMRdev28/app-mobile/pull/7) | Wilaya / commune lists for sign-up and profile update |
| [#9](https://github.com/RMRdev28/app-mobile/pull/9) | Order page |
| [#11](https://github.com/RMRdev28/app-mobile/pull/11), [#13](https://github.com/RMRdev28/app-mobile/pull/13) | Delivery and payment steps of the checkout |
| [#17](https://github.com/RMRdev28/app-mobile/pull/17) | "My purchases" (order history) |
| [#19](https://github.com/RMRdev28/app-mobile/pull/19) | Authentication screens rework |
| [#21](https://github.com/RMRdev28/app-mobile/pull/21), [#22](https://github.com/RMRdev28/app-mobile/pull/22) | 4th order step and home page |
| [#23](https://github.com/RMRdev28/app-mobile/pull/23) | Forgotten password |
| [#25](https://github.com/RMRdev28/app-mobile/pull/25) | UI polish across the app (cart and checkout) |

Merouane set up the project, the home screen, the product integration and the push notifications.

## Architecture

The code is organised **by feature**, with **GetX** for state management, dependency injection and navigation:

```text
lib/
├── features/
│   ├── auth/       # controller, route guard, models, login / sign-up / forgot-password screens
│   ├── home/       # home screen
│   ├── shop/       # product controller and states, product/category models, shop, cart, delivery, payment, order
│   └── profile/    # profile, profile update, orders, order details
├── common/         # reusable widgets: app bar, carousel, product cards
└── utils/          # HTTP client (token auth), theme, constants, validators, formatters, exceptions, helpers
```

## Tech stack

Flutter · Dart · GetX · REST API (`http`, bearer token) · Flutter Secure Storage / GetStorage · Firebase (Core, Storage, Cloud Messaging, Analytics) · carousel_slider · flutter_rating_bar · Git / GitHub (feature branches, pull requests)

## Running it

```bash
flutter pub get
flutter run
```

The app needs the shop's backend API and the Firebase project configuration to work.

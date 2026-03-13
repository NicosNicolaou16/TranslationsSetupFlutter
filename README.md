# Translations Setup Flutter

[![Linktree](https://img.shields.io/badge/linktree-1de9b6?style=for-the-badge&logo=linktree&logoColor=white)](https://linktr.ee/nicos_nicolaou)
[![Static Badge](https://img.shields.io/badge/Site-blue?style=for-the-badge&label=Web)](https://nicosnicolaou16.github.io/)
[![X](https://img.shields.io/badge/X-%23000000.svg?style=for-the-badge&logo=X&logoColor=white)](https://twitter.com/nicolaou_nicos)
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/nicos-nicolaou-a16720aa)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@nicosnicolaou)
[![Mastodon](https://img.shields.io/badge/-MASTODON-%232B90D9?style=for-the-badge&logo=mastodon&logoColor=white)](https://androiddev.social/@nicolaou_nicos)
[![Bluesky](https://img.shields.io/badge/Bluesky-0285FF?style=for-the-badge&logo=Bluesky&logoColor=white)](https://bsky.app/profile/nicolaounicos.bsky.social)
[![Dev.to blog](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge&logo=dev.to&logoColor=white)](https://dev.to/nicosnicolaou16)
[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white)](https://www.youtube.com/@nicosnicolaou16)
[![Static Badge](https://img.shields.io/badge/Developer_Profile-blue?style=for-the-badge&label=Google)](https://g.dev/nicolaou_nicos)

A guide and starter project for implementing **Localization (i18n)** and **Internationalization** in Flutter. This project demonstrates the standard way to handle multiple languages using `flutter_localizations` and the `intl` package.

> [!IMPORTANT]  
> A detailed step-by-step guide is available on Medium!  
> 👉 **[Translation Setup in Flutter with 5 steps](https://medium.com/@nicosnicolaou/translation-setup-in-flutter-with-5-steps-4688ac14ea57)** 👈

## 🚀 Setup Steps

### 1. Update pubspec.yaml

Add the necessary dependencies and enable the `generate` flag.

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations: # add this line
    sdk: flutter # add this line
  intl: ^0.20.2 # add this line

  # Other Code Here

flutter:
  generate: true # add this line

  # Other Code Here

flutter_intl: # add this line
  enabled: false # add this line
```

### 2. Configure l10n.yaml

Create an `l10n.yaml` file in the root of your project to define the input and output directories for your translations.

### 3. Create Translation Files

Add your `.arb` files (e.g., `app_en.arb`, `app_el.arb`) in the designated translations directory.

### 4. Material App Initialization

Configure the `MaterialApp` with the generated localization delegates and supported locales.

```dart
import 'package:flutter_gen/gen_l10n/app_localizations.dart';
import 'package:translations_setup_flutter/translation_screen.dart';

@override
Widget build(BuildContext context) {
  return MaterialApp(
    title: 'Flutter Translation Setup',
    debugShowCheckedModeBanner: false,
    theme: ThemeData(
      colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      useMaterial3: true,
    ),
    // add this code
    localizationsDelegates: const [
      AppLocalizations.delegate,
      GlobalMaterialLocalizations.delegate,
      GlobalWidgetsLocalizations.delegate,
      GlobalCupertinoLocalizations.delegate,
    ],
    // add this code
    supportedLocales: const [
      Locale('en'), // English
      Locale('el'), // Greek
    ],
    home: const TranslationScreen(),
  );
}
```


### 5. Accessing Strings

Use the generated `AppLocalizations` class to access your strings in the UI.

```dart
// import 'package:flutter_gen/gen_l10n/app_localizations.dart'; old import
import 'package:translations_setup_flutter/l10n/app_localizations.dart'; // new import based on the project package

AppLocalizations.of(context)!.helloWorld
```

> [!IMPORTANT]  
> Check my article for the setup :point_right: [Translation Setup in Flutter with 5 steps - Medium](https://medium.com/@nicosnicolaou/translation-setup-in-flutter-with-5-steps-4688ac14ea57) :point_left: <br />

## 🔧 Versioning

- **Flutter SDK:** **3.41.4**
- **Dart Version:** **3.11.1**
- **Intl Package:** **^0.20.2**

## 📚 References & Tutorials

- **Official Documentation:** [Internationalizing Flutter apps](https://docs.flutter.dev/ui/accessibility-and-internationalization/internationalization)
- **Breaking Changes:** [Flutter Generate i10n Source](https://docs.flutter.dev/release/breaking-changes/flutter-generate-i10n-source)

## ⭐ Stargazers

If you find this project useful, please give it a star!  
[Check out the stargazers here](https://github.com/NicosNicolaou16/TranslationsSetupFlutter/stargazers)

## 🙏 Support & Contributions

This project is maintained for the community. Feedback, bug reports, and feature requests are welcome! Feel free to **open an issue** or submit a **pull request**.
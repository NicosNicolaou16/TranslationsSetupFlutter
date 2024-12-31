# Translations Setup Flutter

This project includes the setup for localization and translation in Flutter.

# Setup

## Steps

1) Add the follow setup in pubspec.yaml file.

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations: # add this line
    sdk: flutter # add this line
  intl: ^0.19.0 # add this line

  # Other Code Here

flutter:
  generate: true # add this line

  # Other Code Here

flutter_intl: # add this line
  enabled: false # add this line
```

2) Create the l10n.yaml file under the project directory and initialize the translations directory.

3) Create the translation file(s).

4) Initialize the translation in the Material widget.

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

5) Initialize the String in Text(...) widget.

```dart
import 'package:flutter_gen/gen_l10n/app_localizations.dart';

AppLocalizations.of(context)!.helloWorld
```

> [!IMPORTANT]  
> Check my article for the setup :point_right: [Translation Setup in Flutter with 5 steps - Medium](https://medium.com/@nicosnicolaou/translation-setup-in-flutter-with-5-steps-4688ac14ea57) :point_left: <br />

## Versioning

Flutter SDK version: 3.27.1 <br />
Dart Version: 3.6.0 <br />

# References

https://docs.flutter.dev/ui/accessibility-and-internationalization/internationalization <br />
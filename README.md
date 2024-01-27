# Translations Setup Flutter

This project includes the setup for translation in Flutter.

## Versions

Flutter SDK version: 3.16.9 <br />
Dart Version: 3.2.6 <br />

# Steps

1) Add the follow code in pubspec.yaml file.

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations: # add this line
    sdk: flutter # add this line
  intl: ^0.18.1 # add this line

  # Other code

flutter:
  generate: true # add this line

  # Other code

flutter_intl: # add this line
  enabled: false # add this line
```

2) Create the l10n.yaml file under the project directory and initialize the translations directory.

3) Create the translations file.

4) Initialize the translation in the Material app.

```dart
import 'package:flutter_gen/gen_l10n/app_localizations.dart';
import 'package:translations_setup_flutter/translation_screen.dart';

@override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo Translation Setup',
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

## Check my article

 <br />

# References

https://docs.flutter.dev/ui/accessibility-and-internationalization/internationalization <br />
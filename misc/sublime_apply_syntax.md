## Apply syntax in Sublime

##### Assign syntax with specific extensions
It's really straightforward and does not require any extra plugin:
```
View --> Syntax --> Open all with current extensions as... --> Ruby
```

##### Assign syntax with file names
Some files does not have a extension but it's implicitly associated with a specific syntax. Ex: Podfile (in Cocoapods) --> Ruby, Fastfile (in Fastlane) --> Ruby. Not sure if we could override the Sublime's config to achieve that, I prefer using package `ApplySyntax` for better customization.
```
1. Install package ApplySyntax
2. Sublime Text --> Preferences --> Package Settings --> ApplySyntax --> Settings - User
3. Add a record in "syntaxes":
		{
            "syntax": "Ruby/Ruby",
            "rules": [
                {"file_path": ".*(\\\\|/)Podfile$"},
                {"file_path": ".*(\\\\|/)Fastfile$"}
            ]
        }

```

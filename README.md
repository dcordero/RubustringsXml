# RubustringsXml

Check the format and consistency of the strings.xml files of Android Apps with multi-language support

[Rubustrings](https://github.com/dcordero/Rubustrings) is also available for iOS [here](https://github.com/dcordero/Rubustrings) 

## Usage

It only needs the base strings.xml file and a translated strings.xml file as arguments

```
./rubustringsxml ./res/values/strings.xml ./res/values-es/strings.xml
```

## Validators

Currently Rubustrings validates:

* **The syntaxis of the strings file**: Just checking the xml format of the file
* **Dynamic values (%d, %ld, %s,...)**: It checks that the translation include the same set of them than the original string.
* **Special characters at the beginning or at the end**: If the original string begins or ends with a white space,\n or \r it tests that the translation also does.

It also warning on:
* **Translation significantly large**: In translations 3 times larger than original string

## Example

```
dcordero@silver:~$ ./rubustringsxml res/values/strings.xml res/values-es/strings.xml

Processing files:
 - res/values/strings.xml
 - res/values-es/strings.xml
 
✘ Error, number of variables mismatch: "Phone %s" - "Teléfono"
✘ Error, special beginning mismatch: "\nWeb" - "Web"
⊗ Warning, translation significantly large: "Tubasa" - "Transportes Urbanos de Badajoz"

✘ Some errors detected
```

```
dcordero@silver:~$ ./rubustringsxml res/values/strings.xml res/values-es/strings.xml

Processing files:
 - res/values/strings.xml
 - res/values-es/strings.xml
 
✓ Strings files validated succesfully
```

## Future validators

* Warning on untranslated strings
* Validate strings arrays
* Validate quantity strings

## License

MIT License (MIT) Copyright (c) 2014 @dcordero

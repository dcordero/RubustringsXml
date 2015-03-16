# RubustringsXml

A format validator for Android strings.xml files.

## Usage

It only needs the files to validate as arguments

```
./rubustringsxml ./res/values/strings.xml ./res/values-es/strings.xml
```

## Validators

Currently Rubustrings validates:

* **The syntaxis of the strings file**: Just checking the xml format of the file
* **Dynamic values (%@, %d, %ld,...)**: It checks that the translation include the same set of them than the original string.
* **Special characters at the beginning or at the end**: If the original string begins or ends with a white space,\n or \r it tests that the translation also does.

It also warning on:
* **Translation significantly large**: In translations 3 times larger than original string

## Example

```
dcordero@silver:~$ ./rubustringsxml res/values/strings.xml res/values-es/strings.xml

✘ Error, number of variables mismatch: Phone %s - Teléfono
✘ Error, special beginning mismatch: \nTubasa - Transportes Urbanos de Badajoz
⊗ Warning, translation significantly large: \nTubasa - Transportes Urbanos de Badajoz

✘ Some errors detected
```

```
dcordero@silver:~$ ./rubustringsxml res/values/strings.xml res/values-es/strings.xml
✓ Strings files validated succesfully
```

## License

MIT License (MIT) Copyright (c) 2014 @dcordero

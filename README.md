Library provides functions to handle localization. Translated string
is searched in special files with .lang extention by exact matching
with original string.

Lang files are loaded in memory at program start up from current 
directory. Additional localizations can be loaded with **loadLocaleFile** 
function.

Example:
```
import std.stdio, std.opt;

void main(string[] args) 
{
  string locale;
  getopt(args,
    "l|lang", &locale);

  defaultLocale = locale;
  writeln(dtext("Hello, world!"));
}
```

If text for translation cannot be found in specified locale name, the text will
be saved and written down to a special fuzzy texts file at program shutdown. That
should help to add new localization fast and without program recompilation.

TODO:
* Load localization files on demand;
* Add ability to unload unused locales;
* Add ability to bind texts for arbitrary values (оbjects names, descriptions).

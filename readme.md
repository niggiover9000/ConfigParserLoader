# ConfigParserLoader
This python script contains some useful functions to use with Pythons ConfigParser


# Example Code
## Saving
This example will store the value ``5`` to the section ``settings`` as a variable called ``number``.

````
from config_parser_loader import LoadSettings

loading = LoadSettings()
loading.save_settings("settings", "number", 5)
````
The output in the ``settings.dat`` file will look like this:
````
[settings]
number = 5
````

## Loading
This example will reload the value we saved in the example above. Please note that you can define a fallback value (in
our case thats ``10``) that will be loaded if the value is not found in the file. ``load_settings()`` checks if the 
loaded value is a literal instead of a string and converts it into a literal (e.g. loading a list).
````
from config_parser_loader import LoadSettings

loading = LoadSettings()
loading.open_settings("settings", "number", 10)
variable = loading.load_settings()
print(variable)
````

## Deleting
This example will remove the value we loaded in the example above.
````
from config_parser_loader import LoadSettings

loading = LoadSettings()
loading.delete_settings("settings", "number")
````
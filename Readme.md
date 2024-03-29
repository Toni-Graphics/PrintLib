# PrintLib

PrintLib is a libary for rust which makes printing easy.

> This document is and (works) only for the newest ``PrintLib`` version

[Github reposentory](https://github.com/Toni-Graphics/PrintLib)

## Install

To add PrintLib to your project, go into your project folder and execute:

```bash
cargo add PrintLib
```

Then you can import PrintLib just like other crates:

```rust
use PrintLib::*;
```

## Examples

Link to the examples:
    <https://github.com/Toni-Graphics/PrintLib/tree/master/examples/>

## Documentation

This is the official documentation for the PrintLib.

### Error

The module ``PrintLib::error`` is the module with which you can build error messages.

The ``ErrorFactory`` class

| Function name | Parmaters | Description |
|---------------|-----------|-------------|
|``new``|ecode: ``String``, msg: ``String``| This is the initializer of the class. It creates a new ErrorFactory with the error-code ``ecode`` and the error message ``msg``|
|``add_code_line``|line: ``String``, display_line_no: ``bool``, line_no: ``usize``, display_add: ``bool``|This function adds a new  line to the error message. The parameter ``line`` is the code line of which the error message is specified. ``display_lin_no`` means if the line number (parameter ``line_no`` is the line number) is shown. ``display_add`` means if a +++ needs to be shown (it is good for showing potential fixes).|
|``add_where</code|where_start: ``usize``, where_length: ``usize``, where_msg_b: ``bool``, where_msg: ``String``|This function adds an string to the error message to show where the error is. ``where_start`` means where the showing should start (e.g. where_start = 3 means it starts after the 3rd character). ``where_length`` means how long the showing should be. ``where_msg_b``: when true it showes a string to the right of the showing. When false it shows just the showing. ``where_msg`` is the msg right to the showing (if ``where_msg_b`` is true)|
|``add_arrow``|file: ``String``, line: ``usize``, where_start: ``usize``|Add adds an arrow in the format -->{``file``}:{``line``}:{``where_start``} to the error message|
|``add_arrow_w``|file: ``String``, line: ``usize``, |Add adds an arrow in the format -->{``file``}:{``line``} to the error message|
|``print``||Prints the error message|

### Logger

The module ``PrintLib::logr`` is the module with which you can use the logger.

#### The ``Logger`` Class

| Function name | Parmaters | Description |
|---------------|-----------|-------------|
|``new``| conf | Is the initializer of the class. The parameter ``conf`` is the ``LoggerConfig`` for the class. Returns a new Instance.|
|``debug``|msg: ``String``| Prints the message ``msg`` in level debug|
|``info``|msg: ``String``| Prints the message ``msg`` in level info|
|``warn``|msg: ``String``| Prints the message ``msg`` in level warning|
|``error``|msg: ``String``| Prints the message ``msg`` in level error|

#### The ``def`` function

Returns ``Logger`` with the default configuration

#### The ``LoggerConfig`` struct

| Name | Type | Description |
|---------------|---------|-----------|
|``time``|``bool``|If the time should be presented in logger messages|
|``info_string``|``String``|String which indicates that the message is level info (Normal: [INFO  ])|
|``debug_string``|``String``|String which indicates that the message is level debug (Normal: [DEBUG ])|
|``warn_string``|``String``|String which indicates that the message is level warn (Normal: [WARN!] )|
|``err_string``|``String``|String which indicates that the message is level error (Normal: [[ERR!]  ])|
|``info_color``|``LoggerColor``|The color in which the level indicator ([xyz]) at level info is|
|``debug_color``|``LoggerColor``|The color in which the level indicator ([xyz]) at level debug is|
|``warn_color``|``LoggerColor``|The color in which the level indicator ([xyz]) at level warn is|
|``err_color``|``LoggerColor``|The color in which the level indicator ([xyz]) at level err is|

#### The ``LoggerColor`` struct

| Name | Type | Description |
|---------------|---------|-----------|
|``r``|``u8``|The red channel|
|``g``|``u8``|The green channel|
|``b``|``u8``|The blue channel|

### Color

The module ``PrintLib::colorize`` is the module with which you can colorize your ``&str``s.

#### The ``Colorize`` trait

| Function name | Parameters | Return type | Description |
|---------------|------------|-----------|------------|
|``color``|``&self``, r: ``i16``, g: ``i16``, b: ``116``|``String``|Turns the colorof the string to the specified rgb-values|
|``black``|``&self``|``String``| Makes the string black|
|``red``|``&self``|``String``| Makes the string red|
|``green``|``&self``|``String``| Makes the string green|
|``yellow``|``&self``|``String``| Makes the string yellow|
|``blue``|``&self``|``String``| Makes the string blue|
|``magenta``|``&self``|``String``| Makes the string magenta|
|``cyan``|``&self``|``String``| Makes the string cyan|
|``white``|``&self``|``String``| Makes the string white|
|``gray``|``&self``|``String``| Makes the string gray|
|``bold``|``&self``|``String``| Makes the string bold|
|``italic``|``&self``|``String``| Makes the string italic|
|``underline``|``&self``|``String``| Makes the string underline|
|``strike``|``&self``|``String``| Makes the string strike|
|``bg_black``|``&self``|``String``| Makes the bg of the string black|
|``bg_red``|``&self``|``String``| Makes the bg of the string red|
|``bg_green``|``&self``|``String``| Makes the bg of the string green|
|``bg_yellow``|``&self``|``String``| Makes the bg of the string yellow|
|``bg_blue``|``&self``|``String``| Makes the bg of the string blue|
|``bg_magenta``|``&self``|``String``| Makes the bg of the string magenta|
|``bg_cyan``|``&self``|``String``| Makes the bg of the string cyan|
|``bg_white``|``&self``|``String``| Makes the bg of the string white|
|``bg_gray``|``&self``|``String``| Makes the bg of the string gray|
|``bg_bold``|``&self``|``String``| Makes the bg of the string bold|

#### The ``Style`` struct

| Name | Type | Description |
|-----------|--------|------------|
|``bold``|``bool``|Is the string bold|
|``italic``|``bool``|Is the string italic|
|``underlined``|``bool``|Is the string underlined|
|``strike``|``bool``|Is the string striketrough|

#### The ``ColoredString`` struct

| Name | Type | Description |
|-----------|--------|------------|
|``r``|``i16``|The red color channel|
|``g``|``i16``|The red green channel|
|``b``|``i16``|The red blue channel|

> Side note: If the red channel is -1 there will be no color, but instead a style (like bold, italic, etc.) applied to

| Function name | Parameters | Return type | Description |
|---------------|------------|-----------|------------|
|``new``|r: ``i16``, g: ``i16``, b: ``i16``, _attr: ``Style``, _str: ``&str``|``Colored String``|Initialiser of the colored string class.|
|``to_string``||``String``|Converts the ColoredString to a normal String|

#### The ColorEncoder

``ColorEncoder::encode`` is the function with wich you can turn a simple string with the color names in it into an formated string.

Args: ``str``:   ``&str`` or ``String``

Description: Formats the given string in the correct color which are specified in the string

Colors:
| How it looks like in the string | Actual color |
|---------------------------------|--------------|
|``<black>``|black|
|``<red>``|red|
|``<blue>``|blue|
|``<green>``|green|
|``<yellow>``|yellow|
|``<magenta>``|magenta|
|``<cyan>``|cyan|
|``<white>``|white|
|``<gray>``|gray|
|``<bold>``|bold|
|``<italic>``|italic|
|``<underline>``|underline|
|``<strike>``|striketrough|
|``<&hex>``|hex color|

### Emojis

The module ``PrintLib::emoji`` is the module with which you can make printing emojis easyer.

#### The class ``EmojiMaker``

| Function name | Parameters | Return type | Description |
|---------------|------------|-----------|------------|
|``new``||``EmojiMaker``|Creates a new EmojiMaker|
|``add``|name: ``&str``, emoji: ``&str``||Adds an new emoji with the name ``name``|
|``get``|name: ``str``|``String``|Gets the emoji with the name ``name`` from the intern hashmap|

### Arg

The module ``PrintLib::arg`` is the module with which makes evrything releated to args easyer.

#### The class ``UsageFactory``

| Function name | Parameters | Return type | Description |
|---------------|------------|-----------|------------|
|``new``|name: ``&str``, app_name: ``&str``|``UsageFactory``|Creates a new UsageFactory. ``name`` is the name of your product/application. ``app_name`` is how you would run your programm (e.g for Cargo it would be ``cargo``).|
|``add_cmd``|``&mut self``, name: ``&str``, description: ``&str``||Adds a new command with the name name and description description|
|``add_opt``|``&mut self``, name: ``&str``, description: ``&str``||Adds a new option with the name name and description description|
|``print``|``&mut self``||Prints the usage|

## Errors

Known:

> When bg is changed color do not work proberly

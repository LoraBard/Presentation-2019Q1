# Presentation links

### Task: [https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/Rules.md#md010](https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/Rules.md#md010)
### Presentation: [https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/### Rules.md#md010](https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/Rules.md#md010)
### Transcription: [https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/Rules.md#md010](https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/Rules.md#md010)

## Introduction<hr>

Hello everyone. My name is Tatsiana, and I'll tell you about difference between JSON, YAML and TOML, that are widely used data serialization languages.

When you want to save, send or receive data passed around in application, there are many different serialization formats to choose from. What is the best choice for your use case? I will try to help you to choose most suitable data serialization language for your next project. So let`s start...

## Languages independent<hr>

JSON, YAML and TOML are independent of programming languages. The languages which support these serialization formats include javascript, C, C++, C#, Perl, Java, Python, Php etc.

## What is JSON?<hr>

JSON is one of the simplest data interchange format. It has text-based structure, that makes its easily readable by a human. JSON is often used for serialization and transmission of data between the network connections. It is mostly used for data transmission between a web application and the server. All these cases make JSON so popular alternative to the XML format.

## Some JSON rules

There are several rules that describe the structure of JSON:
- Data inside JSON is represented as key/value pairs. The left side represents the key and the data at the right side represents value. Both key and value are separated by a colon.
- Each key-value pair is separated from the other pair by using a comma.
- keys and values are enclosed in double quotes

JSON provides the following data types:  String, Number, Integer, Boolean, NULL, JSON object.

## Example of JSON file

This is a fragment of JSON file. Curly braces define the JSON objects. Left curly brace represents the start of the object and right curly brace represents the end of the object.Arrays are defined inside a JSON object by using square brackets “[ ]”.

## Some words about YAML<hr>

According to official sources YAML is a human-readable structured data format. It is less complex than JSON, but provides similar capabilities. It essentially allows you to create configuration files.

## Several rules describes YAML`s structure

There are some rules that YAML has:

- YAML files should end in .yaml.
- Yaml files begin with three hyphens (dashes), marking the start of the document.
- YAML is case sensitive.
- YAML does not allow the use of tabs.You must use spaces instead of tabs.

YAML supports the following data types: map, set, null, decimals, hexadecimals, octal integers, fixed and exponential floats, infinity, NAN, boolean, binary type with base 64 encoding.

## Example of YAML file

On this fragment of .yaml file you can see array Book with one element. Each element of the array should start in new line with single hyphen(dash). This fragment, for example,maps the value of book title description and its key title. 

## What is TOML?<hr>

TOML stands for Tom’s Obvious, Minimal Language. It is a data serialisation language designed to be a minimal configuration file format that’s easy to read due to obvious semantics.TOML is an alternative to YAML and JSON. It aims to be more human friendly than JSON and simpler that YAML. TOML is designed to map a hash table. 

## Some facts about TOML syntacsis

- As YAML and JSON, TOML document is based on key/value pairs.
- A TOML file must contain only UTF-8 encoded Unicode characters.
- Whitespace means tab or space.

TOML`s specification includes the following list of supporting data types: String, Integer, Float, Boolean, Datetime, Array, and Table.

## Example of TOML file

The main elements of the TOML document is the key/value pairs. Keys are on the left of the equals sign and values are on the right. Whitespace is ignored around key names and values. The key, equals sign, and value must be on the same line (though some values can be broken over multiple lines). TOML's syntax includes sections enclosed in square brackets.

## Syntactical differences<hr>

Let’s have a look now into the syntactical differences in the most common use cases.

## String<hr>

All formats support Strings. The only difference is that JSON doesn`t support multiline strings.

## TOML multiline string

TOML multiline string are surrounded by three quotation marks. Literal string are surrounded by single quotes. Escaping aren`t allowed.

## YAML multiline string

Strings in YAML can be wrapped both in single and double quotes. In some cases, they can also be unquoted:
- When a string contains line breaks, you can use a special style, indicated by the pipe to indicate that the string will span several lines.
- Alternatively, strings can be written with the folded style, denoted by >, where each line break is replaced by a space.

## Object, table, collection<hr>
JSON object is the same as TOML table and YAML collection.

## TOML table

TOML table is a collection of key/value pair. They appear in square brackets on a line by themselves. Empty tables are allowed and simply have no key/value pairs within them.

## YAML collection

YAML block collections use indentation for scope and begin each entry on its own line. Block sequences indicate each entry with a dash and space. Mappings use a colon and space to mark each key: value pair.

## JSON object

JSON objects are surrounded by curly braces {}.JSON objects are written in key/value pairs.Keys must be strings, and values must be a valid JSON data type.

## Array, list<hr>

List are supported by all languages.

## YAML array

Each element of the array in YAML starts with a string located on a new line with single dash.

## File size<hr>

When serializing large amounts of data important aspect is the verbosity of the format. To compare the verbosity of the different formats, we can pass each format the same data, dump the data to disk, and compare the file sizes.I created 3 files of 3 different formats, which contain 10000 records and 3 that contain 100000 records. The sizes of these files were compared and as expected, the files sizes grow linearly with the number of records. The lightest file was .yaml file.

## Benchmarking<hr>

As to be representative of how the serialization data might be used, all files where passed the same input data. 3 iterations where performed, and the smallest run time of the three was selected as the most representative. Each file included 1000 records. As a result JSON file had the fastest serialization and desiarialization. To track how long an operation takes was used console.time() function.

## YAML parser<hr>
You can parse YAML file by using yaml.load method for serialization and yaml.dunp methodfor desirialization.

## TOML parser<hr>
You can parse TOML file by using toml.parse method for serialization and toml.dunp methodfor desirialization.

## Conclusion<hr>

As a conclusion I want to speak about advantages and desadvantages of each format.

## YAML format. Advantages and disadvantages

### Advantages 

- YAML has a wide variety of uses and popular for. It is often used as configuration file.
- YAML is the superset of JSON. You heard it right. So you can include include JSON fragments into your YAML file and parse it throught  single YAML parser.

### Disadvantages

- There are a lot of extra precautions while writing YAML code. It means that in situation when you mismatch single indent space your code stop working.
- Because of complex syntacsis, as the result of benchmarking, YAML file provide the slowest serialization and deserialization.

## TOML format. Advantages and disadvantages

### Advantages

- TOML was specifically designed to be easier to hand-edit. So TOML has better performance than YAML and JSON.

I compare YAML and JSON because both of them are used as configuration files.

- YAML's syntax is much more complex and subtle than TOML.

### Disadvantages

- Not so fast serialization and deserialization. You can see it in the table.

- TOML can be a little verbose. It can happen when configuration file has a lot of complex nested structures.

## JSON format. Advantages and desadvantages

### Advantages

- JSON is extra popular. Perhaps the most obvious example is the package.json file used by npm and yarn.
- Fast serialization and deserialization.
- JSON is widely supported in JS. JSON has special object JSON, that includes methods for parsing JSON data.

## Desadvantages

- Overly strict. Its restrictiveness is part of what makes it easy to implement a JSON parser, but in my opinion, it also makes JSON file less readability and writability by humans.
- Lack of comments. One feature that is absolutely vital for a configuration language is comments. Comments are necessary to annotate what different options are for and why a particular value was chosen and—perhaps most importantly—to temporarily comment out parts of the config while using a different configuration for testing and debugging. So JSON is not popular as configuration file.
- It doesn’t have any support for multi-line strings. Problem with JSON as a configuration format is it doesn’t have any support for multi-line strings. So if you want newlines in the string, you have to escape them with “\n”.

I hope that this presentation help you to choose right serialization format.
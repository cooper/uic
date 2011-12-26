# Universal Internet Chat

This is version 1 of the Universal Internet Chat protocol.

## 1. Message structure

UIC is a streaming protocol which consists of messages. This section describes the
structure of such messages and events.

### 1.1. Message length

Messages have neither a character limit nor a byte limit.

### 1.2. Separation of messages

Each message is wrapped by brackets (`[` and `]`, ASCII 91 and 93).  

Each message is suffixed by a UNIX-style (LF) newline (`\n`, ASCII 10). It is illegal for
the carriage return (`\r`, 13) to be comprehended as a message terminator. Newlines should
never follow newlines, as that would be considered a blank message.

### 1.3. Message syntax

Messages are written in the following syntax:

```
[COMMAND: PARAMETER(VALUE), OTHER(VALUE)]
```

Where the capitalized words represent the following:

* **COMMAND:** the name of the command being received or sent.
* **PARAMETER:** the value of the command being received or sent.

#### 1.3.1. Parameters and values

The PARAMETER will be suffixed with the VALUE, where the VALUE is in parenthesis (`(` and
`)`, ASCII 40 and 41). The OTHER and second VALUE represent another parameter and value
pair. Parameters are to be separated by a comma (`,`, 44). If a VALUE were to contain
parenthesis, they must be escaped with a backslash (`\`, 92).

#### 1.3.2. Spacing and symbols

The colon (`:`, ASCII 58) after COMMAND is required.  

Spacing has no significant meaning;
the example is spaced only for clarity and readability. It could have also been written as

```
[COMMAND:PARAMETER(VALUE),OTHER(VALUE)]
```

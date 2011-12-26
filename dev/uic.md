# Universal Internet Chat

This is version 1 of the Universal Internet Chat protocol.

## 1. Message structure

UIC is a streaming protocol which consists of messages. This section describes the
structure of such messages and events.

### 1.2. Separation of messages

Each message is separated by a UNIX-style (LF) newline (\n, 10). It is illegal for the
carriage return (\r, 13) to be comprehended as a message terminator. Newlines should never
follow newlines, as that would be considered a blank message.

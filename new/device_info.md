# Device Info Entity

### JSON:

- `id`
  - NOT NULL, length 12
- `name`
  - Changeable device name. For example, `NelonnPC`
- `model`
  - Device Model. `To be filled by O.E.M.` is not allowed, leave it empty in this case
- `platform`
  - Operating system distribution. For example: `Ubuntu`, `macOS` or `Windows`
- `system_version`
  - Operating system distribution version. For example: `22.04` *(Ubuntu)*, `11` *(Windows)*, `13.4` *(macOS)*

### Examples for a few operating systems

Ubuntu 22.04:
```
{
  "platform": "Ubuntu" // not "Linux"
  "system_version": "22.04" // not linux kernel version
}
```

macOS 13.3:
```
{
  "platform": "macOS"
  "system_version": "13.3"
}
```

Windows 11:
```
{
  "platform": "Windows" // without "Home", "Pro", "Education", etc.
  "system_version": "11" // also without "Home", "Pro", "Education", etc.
}
```

Android 13:
```
{
  "platform": "Android" // Not "One UI", "OxygenOS", "MIUI", etc.
  "system_version": "13" // Not SDK version
}
```

iOS 16:
```
{
  "platform": "iOS",
  "system_version": "16"
}
```

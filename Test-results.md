# Test results

Cypress 12.5.1

---
BASELINE

## Windows 11

| Chrome   | Edge     | Electron | Firefox  |
| -------- | -------- | -------- | -------- |
| no error | no error | no error | no error |

## Ubuntu 22.04 under VMware Workstation

| Chrome   | Electron | Firefox  |
| -------- | -------- | -------- |
| no error | no error | no error |

## Ubuntu 22.04 as GitHub runner

| Error      | Chrome | Chromium | Edge | Electron | Firefox |
| ---------- | ------ | -------- | ---- | -------- | ------- |
| ERROR dri3 | 30     | 29       | 28   | 30       | 29      |

Number is line number of error in log.
Error for Electron is:

```text
[1866:0212/100011.310930:ERROR:gpu_memory_buffer_support_x11.cc(44)] dri3 extension not supported.
```

or similar.

---
TEST with:

```yml
env:
  ELECTRON_EXTRA_LAUNCH_ARGS: '--disable-gpu'
```

## Ubuntu 22.04 as GitHub runner

| Error      | Chrome | Chromium | Edge | Electron | Firefox |
| ---------- | ------ | -------- | ---- | -------- | ------- |
| ERROR dri3 | -      | -        | -    | 48       | -       |

Number is line number of error in log.

with
```text
[1867:0212/100023.209663:ERROR:gpu_memory_buffer_support_x11.cc(44)] dri3 extension not supported.
```

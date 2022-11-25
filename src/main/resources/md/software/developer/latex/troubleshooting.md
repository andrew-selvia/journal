# Troubleshooting

Fixing LaTeX compilation problems can be infuriating, especially for novice users. This document records the solutions to problems you may experience along your journey.

## File Not Found

If you see an error like this:

```
! LaTeX Error: File `pgfplots.sty' not found.
```

You may be able to resolve it by installing the missing package like this:

```shell
sudo tlmgr update --self
sudo tlmgr install pgfplots
```

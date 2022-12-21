# IFC.js Monorepo

Purpose of this project is to explore whether building/releasing and dependency management within the IFC.js projects can be made easier by maintaining them as a monorepo managed with lerna.



## Building

```
npx lerna bootstrap
npx lerna run build
```

This will not work if your system does not meet the Prerequisites (below). 

### Prerequisites
* Python
* clone Emscripten as described in [installation](https://emscripten.org/docs/getting_started/downloads.html) docs into a folder we will refer to as `<clone-dir>`.
* Windows:
  - add the emsdk and the `<clone-dir>/emsdk/upstream/emscripten` folder to your PATH variable
  - navigate to `<clone-dir>/emsdk/upstream/emscripten` and run `python emcc.py --generate-config` (creates the `emsdk/upstream/emscripten/.emscripten` config file)
  - in the config file `<clone-dir>/emsdk/upstream/emscripten/.emscripten`, make these changes: 
    - `LLVM_ROOT = '<clone-dir>/emsdk/upstream/bin' `
    - `BINARYEN_ROOT = '<clone-dir>/emsdk/upstream' ` (note the missing `/bin` at the end)


## Automated Releases



# deno-starter

deno-starter with denon. (denon is the replacement for nodemon)

https://github.com/denoland/deno
https://github.com/akifo/deno-starter
https://github.com/eliassjogreen/denon

## Install deno

Refer [deno document](https://github.com/denoland/deno_install).
If it doesn't work in Windows, use `PowerShell`.

## Install denon

- install: `deno install --unstable --allow-read --allow-run -f https://deno.land/x/denon/denon.ts`

## Environment Variables Settings

`.bash_profile`

```bash
# Deno
export DENO_DIR=$HOME/.deno
export PATH=$DENO_DIR/bin:$PATH
```

`Windows`

Make new system variable like 'DENO_PATH'.
And add `%DENO_PATH%` to PATH in system variable.

## deno: tsconfig.json

```
{
  "compilerOptions": {
    "lib": ["es6", "es2018", "dom", "esnext.asynciterable"],
    "target": "es6",
    "module": "commonjs",
    "paths": {
      "deno": ["deno.d.ts"],
      "*.ts": ["./*"]
    }
  }
}
```

## denon configuration

`.denon.json` (you can use one of these `.denon`, `.denonrc`, `.denonrc.json`.)

```
{
  "files": ["src/index.ts"],
  "quiet": false,
  "debug": true,
  "fullscreen": true,
  "extensions": [".js", ".ts", ".py", ".json"],
  "interval": 500,
  "watch": ["src/"],
  "execute": {
      ".js": ["deno", "run"],
      ".ts": ["deno", "run"],
      ".py": ["python"]
  },
  "fmt": false,
  "test": true
}
```

## Command

```bash
$ deno run src/index.ts
```

or Use denon

```bash
$ denon
```

## IT. DOESN'T. WORK!!!

check these.

- did you install deno or denon?
- did you set environment variables?
- check the deno path is right path
- check file path in configuration

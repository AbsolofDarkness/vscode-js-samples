# What is IntelliSense?

IntelliSense is a general term for a variety of code editing features, including: code completion, paramter info, quick info, and list members. 
IntelliSense has been described in a number of ways. 

* IntelliSense is intelligent code completion.
* IntelliSense is docs at your finger tips
* IntelliSense provides instant context aware help. 

In other tools, IntelliSense goes by the terms "code completion", "auto code completion", or "code hinting."

The IntelliSense experience in VS Code is provided by a language service extension. VS Code comes with 

# Using IntelliSense

IntelliSense is very easy to use. Simply type <kbd>ctrl+space</kbd> to trigger IntelliSense. 

You will see IntelliSense as you type, suggesting word completion and methods. 

![animation of IntelliSense](media/intellisense_general.gif)

# Configuring IntelliSense

## Single File

IntelliSense will work for a single file, no problem. You don't need to do anything. 

> Note: if IntelliSense isn't working, run `Reload JavaScript Project` from the command pallate. 

## Entire Workspace

Create a `jsconfig.json` in the root of your workspace. This file indicates to the [Salsa language service](TODO) this is a JavaScript project. 

Each sample contains a `jsconfig.json` file. Here is a simple template you can use. 

```JavaScript
{
  "compilerOptions": {
    "target": "ES6"
  },
  "exclude": [
    "node_modules"
  ]
}
```

The `excludes` attribute is important. This tells the language service what files are and are not part of your source code. If IntelliSense is slow, add folders to your `excludes` list (VS Code will prompt you to do this if it detects the slow down). 

> Note: The file paths in `excludes` are relative to the location of `jsconfig.json`. 

The full documentation for jsconfig.json is here. 

> Tip: For advanced usage, remember that `jsconfig.json` is the same as a `tsconfig.json` file, only with `allowJS` set to true. See [the documentation for `tsconfig.json`](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) here to see other available options. 

## Third Party Modules

TODO typings

# Troubleshooting

## Verify correct setup

1. Do you have jsconfig.json? 
2. Typings

## Report a bug

3. TS Server Trace

```
{
  "typescript.tsserver.trace": "verbose"
}
```

Open the developer tools console. 

> Mac: Help -> Toggle Developer Tools

4. Extensions

```
code --disable-extensions .
```

5. Settings

Copy the contents of your

## Check Samples

This repo contains samples for setting up IntelliSense for JavaScript. If you cannot get IntelliSense to work, compare your project setup with the closest related sample. 

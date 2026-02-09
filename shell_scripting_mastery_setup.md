# Shell Scripting Mastery Setup
_______________________________________________________________________________

```sh
mise ls-remote deno
```

```sh
mise latest deno
```

```sh
mise use deno@2.6.8
```
_______________________________________________________________________________

Add `deno.json` file and a `package.json` file to your project
```sh
touch deno.json
touch package.json
```
_______________________________________________________________________________

Add this to the deno.json file
```json
{
  "nodeModulesDir": "auto"
}
```
_______________________________________________________________________________

#### `"nodeModulesDir": "auto"` explained

By default, deno does not create a `node_modules` directory when installing
npm packages. 

I want the node_modules directory in this project,
so that I can point Neovim to the executable binary 
of the bash language server that I will install later.

_______________________________________________________________________________

```
https://www.npmjs.com/package/bash-language-server
```
_______________________________________________________________________________

```sh
deno add -D --npm --allow-scripts \
bash-language-server@5.6.0
```

Unlike npm, `deno` blocks all `post-install` scripts by default.

If you don't add `--allow-scripts`,

you will get this warning, 
and the `deno approve-scripts` command will fail 
because `core-js` requires node.js.

```
╭ Warning
│
│  Ignored build scripts for packages:
│  npm:core-js@3.48.0
│
│  Run "deno approve-scripts" to run build scripts.
╰─
```

So `--allow-scripts` skips all of this 
and uses deno's npm compatibility layer.

The reason for this issue in the first place is because this 
is a `post-install` script (A set of instructions that run after a package
has been installed).

_______________________________________________________________________________

```sh
touch .gitignore
```

```sh
# npm packages
node_modules/
```
_______________________________________________________________________________

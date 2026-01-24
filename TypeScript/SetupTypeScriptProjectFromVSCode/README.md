# Setup a TypeScript project in Visual Studio Code

YOU CAN JUST DOWNLOAD THE PROJECT, AND FOLLOW UP FROM STEP 22.

1. Create a folder named `TSProject`
2. Open VSC as administrator
3. Open `TSProject` folder in VSC and lunch the `Terminal`
4. Check that _Node.js_ is installed via `node --version`
5. Type `npm init` and press `Enter` until the end. This will result in a default `package.json`
6. Type `npm i -g typescript` to install TypeScript and have access to the `tsc` command
7. Type `tsc --version` to see the TypeScript version
8. Type `tsc --init -sourceMap --rootDir src --outDir dist` to get a `tsconfig.json` (via this command we map the compiled JS files back to 
TypeScript, we set `src` as the source folder for TypeScript files, and `dist` as the destination of the compiled TypeScript files)
9. Create the `src` folder under `TSProject` folder
10. Create in the `src` folder a TypeScript file named `index.ts` (see its content in the above code repo)
11. Click on `Run and Debug` button (or press `F5`)
12. Click on the 'create a launch.json file` link and select `Node.js` from the droplist (this will create the `launch.json` file)
13. At this point, you can successfully run `index.ts` by pressing `F5` (you should see the output in the `DEBUG CONSOLE`
14. Now, let's add a new file, let's name it `person.ts` and update `index.ts` to use it (see their content in the above code repo)
15. At this moment is possible that you'll see this error `A top-level 'export' modifier cannot be used on value declarations in a 
CommonJS module when 'verbatimModuleSyntax' is enabled.ts(1287)`. You can fix this in `tsconfig.json` by setting `verbatimModuleSyntax` to `false`.
Moreover, check `module` and `target` settings to be setup ok.
16. At this moment, we cannot use a file into another file (as in a normal project). Since we try to use `person.ts` in `index.ts`, we
will get an error as `SyntaxError: Cannot use import statement outside a module`. We need to compile TypeScript, and for this go to
`Terminal` and type `tsc`. This creates the `dist` folder. Check this out! It should contains the JavaScript files resulted from compilation
and the source map files to map back to TypeScript.
17. Run the project again via `F5`. This time everthing should work as expected.
18. But, at this time, we need to recompile the project via `tsc` after we modify the source code, and this is cumbersome. It will be more
proper to have a _watcher_ that does this for us, so let's continue with the next step.
19. First, we install a copy of TypeScript locally into the proejct via `npm i --save-dev typescript`
20. Press `F1` and select `Tasks: Configure Default Build Task`
21. Select `tsc: watch - tsconfig.json`. You'll get a ready to go file named, tasks.json.
22. Next, press `F1` and select `Tasks: Run Build Task`. This starts the task in `powershell` as a watcher. This watcher
will react to your changes to recompile the code automatically. Give it a try, and do a modification in `person.ts` and then `F5`.
23. Cool, right? You have a ready to go TypeScript project in VSC!!!





Reproduction Steps
==================

1. Ensure that `jsdom` isn't available, either by removing it from npm, or by
   `unset NODE_PATH`.
2. Run `sbt test` and observe that it succeeds when it should fail.

```
> sbt test; echo $?
[info] Loading settings from plugins.sbt ...
[info] Loading settings from plugins.sbt ...
[info] Loading project definition from /Users/x/tmp/jsdom-bug/project
[info] Loading settings from build.sbt ...
[info] Set current project to my-scala-js (in build file:/Users/x/tmp/jsdom-bug/)
internal/modules/cjs/loader.js:596
    throw err;
    ^

Error: Cannot find module 'jsdom'
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:594:15)
    at Function.Module._load (internal/modules/cjs/loader.js:520:25)
    at Module.require (internal/modules/cjs/loader.js:650:17)
    at require (internal/modules/cjs/helpers.js:20:18)
    at [stdin]:115:13
    at [stdin]:153:3
    at Script.runInThisContext (vm.js:91:20)
    at Object.runInThisContext (vm.js:298:38)
    at Object.<anonymous> ([stdin]-wrapper:6:22)
    at Module._compile (internal/modules/cjs/loader.js:702:30)
[success] Total time: 9 s, completed 26/06/2018 12:44:01 PM
0
```

# babel_win10_dir_symlink
Simple config to test Babel Windows 10 symlinked directory problem 

## Steps to reproduce problem

1. Clone repo
1. `npm i`
1. Run `gulp`

## Results

**Standard Win10 directory**

    [09:36:51] Requiring external module @babel/register
    [09:36:52] Using gulpfile c:\Users\jgroman\Documents\Project\test\gulpfile.babel.js
    [09:36:52] Task never defined: default
    [09:36:52] To list available tasks, try running: gulp --tasks

**Symlinked Win10 directory**  
Created either using `mklink /D` or `mklink /J`

    [09:39:37] Requiring external module @babel/register
    c:\users\jgroman\documents\junctest\gulpfile.babel.js:1
    (function (exports, require, module, __filename, __dirname) { import gulp from 'gulp';
                                                                         ^^^^
    
    SyntaxError: Unexpected identifier
        at new Script (vm.js:80:7)
        at createScript (vm.js:274:10)
        at Object.runInThisContext (vm.js:326:10)
        at Module._compile (internal/modules/cjs/loader.js:664:28)
        at Module._compile (c:\users\jgroman\documents\junctest\node_modules\pirates\lib\index.js:99:24)
        at Module._extensions..js (internal/modules/cjs/loader.js:712:10)
        at Object.newLoader [as .js] (c:\users\jgroman\documents\junctest\node_modules\pirates\lib\index.js:104:7)
        at Module.load (internal/modules/cjs/loader.js:600:32)
        at tryModuleLoad (internal/modules/cjs/loader.js:539:12)
        at Function.Module._load (internal/modules/cjs/loader.js:531:3)

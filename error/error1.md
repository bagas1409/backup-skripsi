Android Bundling failed 404ms node_modules\expo-router\entry.js (1 module)
 ERROR  Error: Cannot find module 'babel-preset-expo'
Require stack:
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\files\plugins.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\files\index.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\index.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\expo\node_modules\@expo\metro-config\build\transform-worker\metro-transform-worker.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\expo\node_modules\@expo\metro-config\build\transform-worker\supervising-transform-worker.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\metro\src\DeltaBundler\Worker.flow.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\metro\src\DeltaBundler\Worker.js
- D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\jest-worker\build\workers\processChild.js

Make sure that all the Babel plugins and presets you are using
are defined as dependencies or devDependencies in your package.json
file. It's possible that the missing plugin is loaded by a preset
you are using that forgot to add the plugin to its dependencies: you
can workaround this problem by explicitly adding the missing package
to your top-level package.json.

    at Function.<anonymous> (node:internal/modules/cjs/loader:1401:15)
    at Module._resolveFilename (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\expo\node_modules\@expo\metro-config\build\transform-worker\utils\moduleMapper.js:128:40)
    at resolve (node:internal/modules/helpers:145:19)
    at tryRequireResolve (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\files\plugins.js:128:11)
    at resolveStandardizedNameForRequire (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\files\plugins.js:162:19)
    at resolveStandardizedName (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\files\plugins.js:183:12)
    at loadPreset (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\files\plugins.js:68:7)
    at loadPreset.next (<anonymous>)
    at createDescriptor (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-descriptors.js:140:16)
    at createDescriptor.next (<anonymous>)
    at evaluateSync (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\gensync\index.js:251:28)
    at D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\gensync\index.js:31:34
    at Array.map (<anonymous>)
    at Function.sync (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\gensync\index.js:31:22)
    at Function.all (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\gensync\index.js:210:24)
    at Generator.next (<anonymous>)
    at createDescriptors (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-descriptors.js:102:41)
    at createDescriptors.next (<anonymous>)
    at createPresetDescriptors (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-descriptors.js:96:17)
    at createPresetDescriptors.next (<anonymous>)
    at D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\gensync-utils\functional.js:22:27
    at Generator.next (<anonymous>)
    at mergeChainOpts (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-chain.js:350:34)
    at mergeChainOpts.next (<anonymous>)
    at chainWalker (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-chain.js:316:14)
    at chainWalker.next (<anonymous>)
    at loadFileChain (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-chain.js:191:24)
    at loadFileChain.next (<anonymous>)
    at mergeExtendsChain (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-chain.js:328:28)
    at mergeExtendsChain.next (<anonymous>)
    at chainWalker (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-chain.js:312:20)
    at chainWalker.next (<anonymous>)
    at buildRootChain (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\config-chain.js:56:36)
    at buildRootChain.next (<anonymous>)
    at loadPrivatePartialConfig (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\partial.js:72:62)
    at loadPrivatePartialConfig.next (<anonymous>)
    at loadFullConfig (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\config\full.js:36:46)
    at loadFullConfig.next (<anonymous>)
    at transform (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\transform.js:20:44)
    at transform.next (<anonymous>)
    at evaluateSync (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\gensync\index.js:251:28)
    at sync (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\gensync\index.js:89:14)
    at stopHiding - secret - don't use this - v1 (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\errors\rewrite-stack-trace.js:47:12)
    at Object.transformSync (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\@babel\core\lib\transform.js:40:76)
    at parseWithBabel (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\expo\node_modules\@expo\metro-config\build\transformSync.js:75:18)
    at transformSync (D:\proyek-kerja\proyek ku\skripsi\cocoa-detector\node_modules\expo\node_modules\@expo\metro-config\build\transformSync.js:64:12)
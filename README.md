Demonstration of a bug with [esbuild-deno-loader].

To reproduce: 

    deno task run   # This works!

Uncomment this line in example.ts:

```typescript
    // ...denoPlugins()
```

Now the above command fails with the error:

```
✘ [ERROR] Expected a JavaScript or TypeScript module, but identified a Unknown module. Importing these types of modules is currently not supported.
  Specifier: file:///Users/codyc/code/bugs/deno-loader-bug/src/style.css [plugin deno-loader]

error: Uncaught (in promise) Error: Build failed with 1 error:
error: Expected a JavaScript or TypeScript module, but identified a Unknown module. Importing these types of modules is currently not supported.
  Specifier: file:///Users/codyc/code/bugs/deno-loader-bug/src/style.css
    at failureErrorWithLog (file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:1651:15)
    at file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:1059:25
    at runOnEndCallbacks (file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:1486:45)
    at buildResponseToResult (file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:1057:7)
    at file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:1086:16
    at responseCallbacks.<computed> (file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:704:9)
    at handleIncomingPacket (file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:764:9)
    at Readable.readFromStdout (file:///Users/codyc/Library/Caches/deno/npm/registry.npmjs.org/esbuild/0.20.2/lib/main.js:680:7)
    at Readable.emit (ext:deno_node/_stream.mjs:1851:9)
    at addChunk (ext:deno_node/_stream.mjs:2873:16)
```



[esbuild-deno-loader]: https://github.com/lucacasonato/esbuild_deno_loader
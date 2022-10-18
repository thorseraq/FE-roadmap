### Indicate a directory as a TypeScript project.
📫 link: [What is a tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)<br/>

A tsconfig.json file or xxx.json in the current directory or parent directory can be recognized by TypeScript cli - [**tsc**](https://www.typescriptlang.org/docs/handbook/2/basic-types.html#tsc-the-typescript-compiler). 

### How TypeScirpt project is structured using import/export: 
📫 link: [Modules](https://www.typescriptlang.org/docs/handbook/modules.html)<br/>
TypeScript implements an ECMAScript 2015(ES6) style module-loading systems, and is capable of compiling the project to various module-loading system, such as Node.js (CommonJS), require.js (AMD), UMD, SystemJS or ECMAScript 2015 native modules (ES6) . This can be configured by [module](https://www.typescriptlang.org/tsconfig#module) in the tsconfig.json file. Therefore, in TypeScript project there is no need worrying about the target platform where compiled javascript files are running, as different platforms may require different module system.

⚡ example: cnofiguring the target module-loading system
```json
{
  "compilerOptions": {
    "module": "commonjs"
  }
}
```

### How typescript module system resolves module path
📫 link: [Module Resolution](https://www.typescriptlang.org/docs/handbook/module-resolution.html)<br/>

There are two types of paths when `import {SomeClass} from "some_path_is_put_here"`: Relative path and Non-relative path. When resolving there two kinds of paths, two strategies are used, Classic(for backwards compatibility) and Node(recommended). These two are similar. Very detailed examples are showed in above article. [baseUrl](https://www.typescriptlang.org/tsconfig#baseUrl) and [paths](https://www.typescriptlang.org/tsconfig#paths) can be configured to impact non-relative path resolving. Note once path is configured to imply path mapping, non-relative resolving rule will be breaked. Examples in [Path-mapping](https://www.typescriptlang.org/docs/handbook/module-resolution.html#path-mapping) shows this.



### A test framework testing for modern web apps.
📫 link: [Playwright](https://playwright.dev/)

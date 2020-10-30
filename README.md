Reproducer for Issue 626
========================

Issue here: https://github.com/rollup/plugins/issues/626


To reproduce:

```bash
npm i && npm run build
```

Should out the following issue:

```
node_modules/@rollup/plugin-typescript/types/index.d.ts:38:73 - error TS2344: Type 'CustomTransformers[T]' does not satisfy the constraint 'any[]'.
  Type '(TransformerFactory<SourceFile> | CustomTransformerFactory)[] | (CustomTransformerFactory | TransformerFactory<SourceFile | Bundle>)[] | undefined' is not assignable to type 'any[]'.
    Type 'undefined' is not assignable to type 'any[]'.

38 type StagedTransformerFactory<T extends TransformerStage> = ElementType<CustomTransformers[T]>;
                                                                           ~~~~~~~~~~~~~~~~~~~~~

node_modules/@rollup/plugin-typescript/types/index.d.ts:51:20 - error TS2304: Cannot find name 'Program'.

51   factory(program: Program): StagedTransformerFactory<T>;
                      ~~~~~~~

node_modules/@rollup/plugin-typescript/types/index.d.ts:57:24 - error TS2304: Cannot find name 'TypeChecker'.

57   factory(typeChecker: TypeChecker): StagedTransformerFactory<T>;
                          ~~~~~~~~~~~


Found 3 errors.
```

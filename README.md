# node-allgemein-packaging

Use 
``` 
npx allg-packaging
```
to update necessary dev dependencies for predefined gulp tasks.
Additionally a gulpfile.ts will be created with following content:

``` 
import * as glob from 'glob';

[
  ...glob.sync('node_modules/*/gulp/*'),
  ...glob.sync('src/gulp/*'),
  ...glob.sync('gulp/*'),
]
  .filter(x => !/@types\//.test(x))
  .map(x => require('./' + x));
```

You can create own gulp tasks or extend the existing in the predefined directories:

* gulp
* src/gulp

Tasks:
``` 
gulp --tasks
```

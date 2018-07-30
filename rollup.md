### rollup打包vue2组件

```javascript
npm i minimist rollup rollup-plug
in-buble  rollup-plugin-uglify-es rollup-plugin-vue vue vue-template-compiler --save


import babel from 'rollup-plugin-babel';
import resolve from 'rollup-plugin-node-resolve';
import vue from 'rollup-plugin-vue';
import replace from 'rollup-plugin-replace'
import image from 'rollup-plugin-image';
import buble from 'rollup-plugin-buble';
import uglify from 'rollup-plugin-uglify-es';
import minimist from 'minimist';

export default {
  entry: 'src/main.js',
  format: 'cjs',
  plugins: [ vue(), replace({
      'process.env.NODE_ENV': JSON.stringify('development'),
      'process.env.VUE_ENV': JSON.stringify('browser')
    }),
    resolve(), babel() ],
  dest: 'dist/bundle.js' // 输出文件
};
```

https://github.com/qiqihaobenben/rollup-demos
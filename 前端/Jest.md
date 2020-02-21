# Jest

## 配置

### Jest + Node + Babel

Jest 在 Node 环境中不识别 ES 模块，只识别 CommonJS 模块，所以需要借助于 Babel 来做转换。安装以下类库：

```bash
yarn add @babel/core @babel/preset-env --dev
```

`.babelrc` 配置如下：

```json
{
  "presets": [
    ["@babel/preset-env", {
      "targets": {
        "node": "current"
      }
    }]
  ]
}
```

配置说明参见 [@babel/preset-env](https://babeljs.io/docs/en/babel-preset-env#targetsnode)。

原理过程：

1. yarn jest
2. jest (babel-jest)
3. babel-core
4. 读取 `.babelrc` 配置
5. 运行测试前，结合 babel，先将代码做一次转化
6. 运行转化过的测试用例代码

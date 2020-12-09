# vue-toy-block

## 一、项目配置

### 1. 规范 commit 配置

`commitizen` 是一款标准化的 `git commit` 信息的工具，通过该工具可以帮助开发者规范 commit 信息。

**安装流程**

**Step 1**

1. `npm install -D commitizen`
2. `npm install cz-conventional-changelog -D`
3. `package.json` 中添加如下配置

```
"config": {
    "commitizen": {
      "path": "./node_modules/cz-conventional-changelog"
    }
  }
```

安装并添加完成后，既可使用 `git cz` 命令替换 `git commit` 来使用了。

**Step 2**

添加 commit 信息校验功能，限制开发者必须使用 `git cz` 来提交 commit。

1. `npm install -D husky`
2. `npm install -D validate-commit-msg`
3. `package.json` 中添加如下配置

```
"config": {
    "validate-commit-msg": {
      "helpMessage": "ERROR: please use 'git cz' to commit changes"
    }
  },
  "husky": {
    "hooks": {
      "commit-msg": "validate-commit-msg"
    }
  }
```


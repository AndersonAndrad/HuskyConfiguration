# Husky Configuration

<a href="https://github.com/typicode/husky">
  <img src="https://img.shields.io/badge/github-huksy-blue?style=flat-square&logo=appveyor"></a>

### Welcome, this is just a configuration for better documentation and organization of your commits, I will leave the necessary links to check the documentation of the tools used in this project, then the implementation documentation (The same can be found in the links that I will let them be the officers)

**OBS:** *During the installation I will be using yarn, but you can use another package installer of your choice*

```
yarn add husky @commitlint/{config-conventional,cli} @commitlint/config-conventional @commitlint/cli commitizen
```

```
# Configure commitlint to use conventional config
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
```

```
commitizen init cz-conventional-changelog
```

Place the following code inside your package.json file

```
"husky": {
  "hooks": {
    "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
    "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true"
  }  
},
```

Try commit your project 

```
git add .
and 
git commit 
```


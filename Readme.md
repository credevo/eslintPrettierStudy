# **eslint & prettier practice**




>## 기본적으로 eslint의 권장되는 것 적용할수 있는 방법

.eslintrc.js
```js
extends: [
    "eslint:recommended"
]
```

>## 프리티어 포매팅 규칙을 eslint로 추가하고

서로 충돌하는 옵션이 있으면,

프리티어의 규칙을 사용하도록 하는 도구 입니다.

```console
npm i -D eslint-config-prettier eslint-plugin-prettier
```

.eslintrc.js 플러그인 추가
```js
extends: [
    "eslint:recommended",
    "plugin:prettier/recommended"
]

```

>## husky hooks : pre-commit

commit 되기전 명령어 설정하도록 하는것을 lint 로 설정
```console
npm i -D husky
```

package.json
```json
"husky" : {
    "hooks" : {
    "pre-commit" : "npm run lint"
    }
}
```

>## lint-staged 
staging 파일중 js파일만 린트 검사하도록 설정
```console
npm i -D lint-staged
```

package.json
```json
"lint-staged" : {
    "*.js" : "npm run lint" // 명령어 셋팅
}
```

변경 : 커밋하기전 린트 하도록 설정
```json
"husky" : {
    "hooks" : {
    "pre-commit" : "lint-staged"
    }
}
```
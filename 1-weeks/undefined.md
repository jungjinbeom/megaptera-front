# 😝 개발 환경

### 개발 환경 세팅

ToolChain이라 불리는 도구들의 모음들이 있는데 대부분 Node.js를 기반으로 한다.

도구들이 계속 생기고 있기때문에 상황에 맞는 도구들을 사용하기 어려움

전체적인 흐름을 파악하고 앞으로의 변경에 대응할수 있는 능력을 키우는게 중요하다. \


### JavaScript 개발 환경 (Node.js) 세팅

* fnm(Fast Node Manager)
  * Node 버전 관리자로 Nvm보다 빠르다.
* Node.js 공식 문서 &#x20;
  * 짝수버전은 안정적인 버전 홀수버전은 최신 버전이다.
  * 현재 버전은 최신 버전이지만 안정적으로는 사용하기 힘들고 LTS(LongTermSoft)는 말그대로 안정적인 버전을 사용할 수 있다.



### TypeScript + React + Jest + Parcel 개발 환경 세팅

#### 작업할 폴더 준비

<pre class="language-sh"><code class="lang-sh"><strong>mkdir 폴더명 
</strong>
cd 폴더명 

#code. 명령어를 사용해서 VSCode를 쉽게 열수 있다. 
code .
</code></pre>

#### npm 패키지 준비&#x20;

```shell
npm init -y
```

#### .gitignore 파일 작성&#x20;

* node\_modules를 통째로 커밋하는 일을 방지하기 위해 사용
* .gitignore 페이지를 생성해주는 사이트를 이용해도 좋다.
* github에서 repository 생성 시 기본으로 제공해준다.

#### TypeScript 설정

```sh
# -D를 붙이는 이유는 개발 환경에서만 사용하기위해 -D붙여서 install 한다.
# tool로 사용하는 것들에 대해서 개발 환경에 설치할때 사용
# 서버에 배포할 때 빼고 설치가 가능하다. 배포시 용량을 줄일 수 있다.

#개발환경에 타입스크립트 설치
npm i -D typescript

#TypeScript 설정 파일 생성
npx tsc --init

#tsconfing 파일에서 jsx 속성 변경을 한다 
```

### EsLint 설정

```sh
npm i -D eslint

npx eslint --init

# jest도 같이 잡아주면 좋다. 
# jest:true

touch .eslintignore

#현재 폴더의 처리
npx eslint -fix .
```

### React 설치&#x20;

```sh
npm i react react-dom

npm i -D @types/react @types/react-dom
```

### 테스팅 도구 설치&#x20;

```sh
npm i -D jest @types/jest @swc/core @swc/jest \
    jest-environment-jsdom \
    @testing-library/react @testing-library/jest-dom
    
#jest.config.js 파일 생성 및 작성 후 테스트에서 SWC를 사용하자 
```

### Parcel 설치

```sh
npm i -D parcel
```

### &#xD;

## 학습 키워드

### npx

```sh
# npx란 npm의 도구이다 
# 패키지를 임시 설치 및 실행할 때 사용한다.
# npx 사용 예제 
# ./node_modules/.bin/tsc --help => npx tsc --help 으로 변경해서 사용가능 
```

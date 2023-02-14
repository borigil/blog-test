---
title: Nuxt 시작하기
tags: nuxtjs, vuejs
date: 2023-03-14
description: Nuxtjs 설치 및 초기세팅
image: https://i.ytimg.com/vi/PkdY8vfNxQs/maxresdefault.jpg
draft: true
---

# Nuxt 시작하기
이번 게시글에서는 Nuxt를 시작해 볼 것인데,

nuxt2/ nuxt bridge/ nuxt3 프로젝트를 각각 생성해보고 실행해 볼까 한다.

 

당연히 공식문서 기반으로 따라 해볼까 한다.

Nuxt2
Nuxt2는 create-nuxt-app을 사용하여 간편하게 프로젝트를 생성할 수 있다.

yarn/npx/npm에 따라 명령어가 조금씩 달라지기는 한다.

yarn create nuxt-app <project-name>
npx create-nuxt-app <project-name>
npm init nuxt-app <project-name>
해당 명령어를 입력해보면 하나하나 생각보다 많은 설정을 선택해야 한다.


그래도 크게 어려운 거는 없으니 본인 환경에 맞게 설정해주면 된다.

만약 처음부터 완벽하게 할 거야!라고 생각한다면 하나하나 설명해주는 친절한 블로그가 있길래 링크를 달아둔다.

https://kadamon.tistory.com/29

 
1. Nuxt.js - 설치하기

Nuxt.js - 설치하기 1. Mac 에 설치 공식문서에 따르면 크게 두가지 방식이 있는 것으로 보입니다. create-nuxt-app을 이용하여 project 구조를 미리 잡아 놓고 시작. package.json 부터 완전 밑바닥 부터 세팅.

kadamon.tistory.com
일단 나는 yarn 보다는 아직은 npm 위주로 사용하기 때문에 npm을 활용하여 프로젝트를 생성하였다.\

 

생성이 완료되면 다음과 같이 프로젝트가 생성된다.


생각보다 설정 파일만 빼면 조촐하게 되어있다.

예전에는 좀 더 많은 폴더들을 기본적으로 제공해 주었던 기억이 있는데,

버전이 업되면서 기본적으로 제공해주던 폴더들은 생략되었고 필요에 따라 추가하면 되는 것으로 보인다.

 

각 폴더별로 역할이 있으니 폴더 구조에 대해서는 공식문서를 살펴보는 게 좋을 거 같다.

https://nuxtjs.org/docs/directory-structure/nuxt

 
Nuxt build directory

The .nuxt directory is the so-called "build directory". It is dynamically generated and hidden by default. Inside the directory you can find automatically generated files when using nuxt dev or your build artifacts when using nuxt build.

nuxtjs.org
 

그리고 이제 생성된 nuxt2 프로젝트 폴더로 들어가서 실행 명령어를 입력해주자.

yarn dev
npm run dev
그러면 실행이 된다는 로그가 출력되면서 실행됐는지 확인을 해보면 아래와 같은 창으로 들어갈 수 있다.


 

참고: https://nuxtjs.org/docs/get-started/installation/

 
Installation

Here, you will find information on setting up and running a Nuxt project in 4 steps.

nuxtjs.org
Nuxt Bridge
Nuxt Bridge는 참... 난감하다.

Nuxt2와 Nuxt3처럼 프로젝트 생성하는 명령어가 따로 존재하는 게 아니라 Nuxt2에서 Nuxt Bridge로 migrate 해줘야 한다. (내가 못 찾은 걸 수도 있는데, 아무리 찾아봐도 없다.)

 

애초에 Nuxt Bridge는 Nuxt2 프로젝트에서 Nuxt3을 맛보기 위해 나온 게 아닌가?라고 알고 있다.


그래서 그런지 공식문서에서도 만약 새로운 프로젝트를 만든다면 Nuxt Bridge를 타고 넘어갈게 아니라 바로 Nuxt3로 시작하라고 안내해 주고 있다.

 

우선적으로 살펴볼 사이트는 공식 깃허브 사이트이다.

https://github.com/nuxt/bridge

 
GitHub - nuxt/bridge: 🌉 Experience Nuxt 3 features on existing Nuxt 2 projects

🌉 Experience Nuxt 3 features on existing Nuxt 2 projects - GitHub - nuxt/bridge: 🌉 Experience Nuxt 3 features on existing Nuxt 2 projects

github.com
또 다른 사이트는 굳이 깃허브까지 갈 필요 없이 공식문서에 Upgrade Guide가 존재하는데, 거기를 살펴봐도 좋다.

내용 자체는 위 깃허브와 다를 게 없지만 알아두면 좋을 것 같다.

https://nuxt.com/docs/getting-started/upgrade

 
Upgrade Guide · Get Started with Nuxt

Have a Nuxt 2 project to migrate? Use these guides to upgrade your Nuxt applications to Nuxt 3 or take the first step in that direction with Nuxt Bridge. If you are already using Nuxt 3 and want to upgrade to the latest release or test new features before

nuxt.com
 

자세한 과정은 위 공식문서들을 살펴보는 게 좋겠고,

나 같은 경우에는 새로 만든 Nuxt2 프로젝트를 Nuxt Bridge로 마이그레이션 하는 것이기 때문에 크게 어렵거나 하지 않았다.

 

우선 기존 설정에 영향을 받는 폴더(.nuxt/ node_modules/package-lock.json)을 제거해주었다.

추가적으로 더 있는 경우에는 그것 역시 제거해 주는 게 좋다.

 

그리고 공식문서에 나와 있는 기본적인 부분에 대해서만 설정해 주었다.

우선 package.json에서 아래와 같이 수정해주고. (-는 빼고 +는 추가하라는 건 굳이 설명 안 해도 알 것이다.)

- "nuxt": "^2.15.0"
+ "nuxt-edge": "latest"
npm install을 통해 package.json에 있는 라이브러리들을 다시 받아주자.

그리고 Nuxt Bridge를 추가해 줄 것이다.

yarn add --dev @nuxt/bridge@npm:@nuxt/bridge-edge
npm install -D @nuxt/bridge@npm:@nuxt/bridge-edge
 

그다음에는 package.json에 있는 scripts를 수정해 줄 것이다.

{
 "scripts": {
 - "dev": "nuxt",
 + "dev": "nuxi dev",
 - "build": "nuxt build",
 + "build": "nuxi build",
 - "start": "nuxt start",
 + "start": "nuxi preview"
 }
}
그리고 nuxt.config에 defineNuxtConfig를 추가해 줄 것이다.

import { defineNuxtConfig } from '@nuxt/bridge'

export default defineNuxtConfig({
  // Your existing configuration
})
(만약 tsconfig.json이 있다면 공식문서를 참고하길 바란다.)

 

본인 환경에 따라서 추가 작업을 해줘야 할 것들이 있으니 꼭 공식문서를 참고하길 바란다.

나 같은 경우에는 그냥 기본적인 설정과 새로운 프로젝트 대상으로 마이그레이션을 한 거라 크게 어렵지는 않았다.

 

이제 다시 npm run dev를 통해 서버를 실행시키면 nuxt bridge로 정상적으로 실행된다.


nuxt bridge가 맞는지 확인하려면 composition api를 사용해 보는 것을 추천한다.

Nuxt3
Nuxt3는 다행히 프로젝트 생성 명령어가 존재하므로 아주 간단하다.

 

만약 Nuxt2에서 마이그레이션 할 예정이라면 공식문서의 Upgrade Guide를 참고하고,

새로운 프로젝트 생성은 npx 또는 pnpm을 통해 생성하도록 하자.

npx nuxi init <project-name>
pnpm dlx nuxi init <project-name>
해당 명령어를 실행하면 아주 내용이 부실한 프로젝트가 하나 생성될 것이다.

(재밌는건 nuxt2처럼 설정을 선택하는 화면이 나오지는 않고 바로 아래와 같이 생성된다.)


정말 아무것도 없다 신기하게도.

그다음에는 해당 폴더로 들어가서 package.json에 있는 내용들을 추가해주자.

yarn install
npm install
pnpm install
해당 작업이 완료되었다면 npm run dev 같은 명령어로 서버를 실행시켜주면 정상적으로 동작한다.


Nuxt3의 경우에는 기본적으로 제공하는 게 거의 아무것도 없다시피 하여 필요한 부분들은 직접 추가해줘야 한다.

폴더 구조의 경우에는 공식문서에서 안내해주고 있으니 참고하면서 환경을 잡아가면 된다.

https://nuxt.com/docs/guide/concepts/auto-imports

 
Auto imports · Nuxt Concepts

Nuxt auto-imports helper functions, composables and Vue APIs to use across your application without explicitly importing them. Based on the directory structure, every Nuxt application can also use auto-imports for its own components, composables and plugin

nuxt.com
nuxt2도 점점 nuxt3처럼 최소한의 폴더만 제공해주는 것으로 보인다.

 

참고: https://nuxt.com/docs/getting-started/installation
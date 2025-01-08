---
title: (Fuwari) Fuwari 테마 깃허브 블로그 만들기
published: 2024-11-06
description: 'Fuwari 템플릿을 이용해 깃허브 블로그를 만드는 방법에 대한 소개'
image: ''
tags: [가이드, 깃허브, Fuwari, Astro]
category: 'Fuwari'
draft: false 
---

:::tip
만약 게시글을 따라 블로그를 만드는 중에 오류가 발생했다면, [**여기**](/posts/fuwari/errors-encountered-while-creating-a-blog/)를 클릭해 참고해주세요.
:::

## 소개 및 용어 설명

### Fuwari란?

`Fuwari`란 `Astro`로 구축된 정적 블로그 템플릿입니다.

::github{repo="saicaca/fuwari"}

데모 사이트: https://fuwari.vercel.app/

#### 특징

- [Astro](https://astro.build) 및 [Tailwind CSS](https://tailwindcss.com)로 구축됨
- 부드러운 애니메이션 및 페이지 전환 + 반응형 디자인
- 사용자 정의 가능한 테마 색상 및 배너
- 라이트 모드 / 다크 모드 지원
- 검색, 목차 기능 지원

### 깃허브 블로그란?

깃허브 블로그란 `GitHub Pages`를 이용해 무료로 만들 수 있는 블로그를 말합니다.

### GitHub Pages란?

[**Github Pages**](https://docs.github.com/ko/pages)란 깃허브 저장소의 파일을 웹사이트로 호스팅해주는 기능입니다.

주로 정적 웹사이트 생성기인 `Jekyll`이나 `Astro`, `Hexo` 같은 도구를 사용해 사이트를 생성하고, GitHub에 푸시하여 배포합니다.

### Astro란?

`Astro`란 정적 사이트 생성기이자 웹 프레임워크입니다.

빠르고 가볍게 블로그와 같은 콘텐츠 중심 웹사이트를 웹사이트를 구축할 수 있게 해줍니다.

[**Astro 프로젝트 구조**](https://docs.astro.build/ko/basics/project-structure/)

---

## 새 리포지토리 생성

https://github.com/new

새로운 리포지토리의 이름은 `<username>.github.io` 로 해야합니다.

---

## 리포지토리 복제

`git clone` 후 클론한 폴더로 이동합니다.

```bash
git clone https://github.com/saicaca/fuwari.git
cd fuwari
```

---

## 의존성 패키지 설치

:::important
아직 [pnpm](https://pnpm.io)을 설치하지 않았다면 `npm install -g pnpm`을 실행하여 [pnpm](https://pnpm.io)을 설치하세요.
:::

다음 명령어를 실행해 의존성 패키지를 설치합니다.

```bash
pnpm install && pnpm add sharp
```

---

## 블로그 구성 파일 편집

`src/config.ts` 열어서 블로그를 커스터마이징(사이트 제목, 프로필 사진 등) 할 수 있습니다.

구체적인 내용은 [여기](/posts/fuwari/config-file-description/)를 클릭해 확인할 수 있습니다.

---

## Github Pages용 Astro 구성

GitHub 페이지에 배포하기 위해서는 배포하기 전에 Astro 구성 파일 `astro.config.mjs` 을 편집해야 합니다.

### github.io URL로 사이트 구성 편집

`astro.config.mjs`에서 아래와 같이 site 및 base 옵션을 설정합니다.

```yml
export default defineConfig({
  site: 'https://<username>.github.io',
  base: '/',
```

### GitHub Actions 파일 구성

프로젝트 최상단에서 `.github/workflows/deploy.yml` 파일을 만들고 아래 내용을 붙여넣습니다.

```yml
name: Deploy to GitHub Pages

on:
  # 'main' 브랜치로 푸시할 때마다 워크플로를 트리거합니다.
  # 다른 브랜치 이름을 사용하시나요? `main`을 브랜치 이름으로 바꾸세요.
  push:
    branches: [ main ]
  # GitHub의 Actions 탭에서 이 워크플로를 수동으로 실행할 수 있습니다.
  workflow_dispatch:

# Allow this job to clone the repo and create a page deployment
permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout your repository using git
        uses: actions/checkout@v4
      - name: Install, build, and upload your site
        uses: withastro/action@v3
        # with:
          # path: . # 저장소 내 Astro 프로젝트의 루트 위치입니다. (선택 사항)
          # node-version: 20 # 사이트를 빌드하는 데 사용해야 하는 특정 버전의 Node입니다. 기본값은 20입니다. (선택 사항)
          # package-manager: pnpm@latest # 종속성을 설치하고 사이트를 빌드하는 데 사용해야 하는 노드 패키지 관리자입니다. lockfile을 기반으로 자동으로 감지됩니다. (선택 사항)

  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### 리포지토리 GitHub Actions 설정

GitHub에서 본인의 github.io 리포지토리의 Settings 탭으로 이동하여 `Pages` 섹션을 찾은다음

사이트의 Source로 `GitHub Actions`를 선택하세요.

---

## 블로그 로컬 테스트

`pnpm dev` 명령어를 실행한 뒤 `localhost:4321`에 접속해 로컬에서 블로그가 제대로 동작하는지 확인할 수 있습니다.

---

## 새 리포지토리에 로컬 파일 푸시

아래의 명령어들을 차례대로 실행하세요.

- 원격 리포지토리를 자신의 `github.io` 로 변경

```bash
git remote set-url origin <repository-url>
```

- Git Credential Manager 사용 설정

```bash
git config --global credential.helper manager
```

- 사용자 이메일과 이름을 설정

```bash
git config user.email "you@example.com"
git config user.name "Your Name"
```

- 모든 파일 스테이징

```bash
git add .
```

- 커밋 메시지 작성

```bash
git commit -m "Initial commit for GitHub Pages blog"
```

- 변경사항 푸시

```bash
git push origin main
```

---

## 배포된 깃허브 블로그 접속

여기까지 따라한 뒤에 워크플로가 성공했으면 `https://<username>.github.io`로 접속해 정상적으로 사이트에 접근 할 수 있습니다.

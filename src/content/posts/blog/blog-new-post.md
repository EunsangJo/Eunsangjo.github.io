---
title: Fuwari - 첫 글 게시하기
published: 2024-11-08
description: 'Fuwari 템플릿 블로그에서 새 게시물을 생성하는 방법 소개'
image: ''
tags: [깃허브, Fuwari, Astro]
category: 'Blog'
draft: false 
---

Astro 기반의 Fuwari 템플릿 블로그는 마크다운 문법으로 게시물을 작성 가능

## 새 게시물 생성

프로젝트 최상단, 터미널에서 다음 명령어를 실행

```bash
pnpm new-post <filename>
```

실행 후 `src/content/posts/`위치에 `<filename>.md` 파일이 생성됨

해당 파일을 열어 게시물의 머리말과 내용을 작성

## 게시물의 머리말 설정 예시

```yaml
---
title: 내 첫 블로그 게시물
published: 2024-11-08
description: 내 새로운 Astro 블로그의 첫 번째 게시물입니다!
image: /images/cover.jpg
tags: [푸, 바, 오]
category: 앞-끝
draft: false
---
```

| Attribute     | Description                                                                                                                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`       | The title of the post.                                                                                                                                                                                      |
| `published`   | The date the post was published.                                                                                                                                                                            |
| `description` | A short description of the post. Displayed on index page.                                                                                                                                                   |
| `image`       | The cover image path of the post.<br/>1. Start with `http://` or `https://`: Use web image<br/>2. Start with `/`: For image in `public` dir<br/>3. With none of the prefixes: Relative to the markdown file |
| `tags`        | The tags of the post.                                                                                                                                                                                       |
| `category`    | The category of the post.                                                                                                                                                                                   |
| `draft`        | If this post is still a draft, which won't be displayed.                                                                                                                                                    |

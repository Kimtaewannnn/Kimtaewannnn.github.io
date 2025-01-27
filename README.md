## 글 작성하기

**1. `_data/authors.yml`에  정보 등록**

```yaml
- name: 웹사이트에서 표시될 이름
  email: 글 하단 signature에 표시될 이메일
  image: 프로필 이미지
```

**2. `_tags`디렉토리에 사용할 새 태그 생성**

```
---
title: 웹사이트에서 표시될 이름
identifier: post에서 사용될 식별자(소문자, 띄어쓰기 대신 하이픈 사용)
description: 태그 페이지에 표시될 설명
---
```

**3. `_posts`디렉토리에 `yyyy-mm-dd-제목.md`파일 생성**
**4. 해당 파일 Front Matter 작성**

```
---
title: 웹사이트에서 표시될 이름
tags: [앞서 작성한 태그의 identifier, 여러개 가능]
author: 앞서 작성한 작성자의 name
---
```

## 포트폴리오 추가하기

**1. `_data/portfolio.yml`에 하단 구문 추가**

```yaml
- title: 표시될 이름
  description: 이름 하단에 들어갈 설명
  image: <assets/images/portfolio/>내에 위치한 이미지 파일의 이름(확장자 포함)
```

## 프로젝트 추가하기

**1. `_projects`디렉토리에 `제목.md`파일 생성**

**2. 해당 파일 작성**

```yaml
---
title: 프로젝트 제목
description: 프로젝트 설명
image: <assets/images/projects/>내에 위치한 이미지 파일의 이름(확장자 포함)
date: 프로젝트 시행 날짜(yyyy-mm-dd) - 정렬에 사용됩니다.
---
내용
```

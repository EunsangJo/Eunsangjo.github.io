---
title: ComfyUI Desktop으로 AI 그림질 시작하기
published: 2025-01-08
description: ""
image: ""
tags: [ComfyUI, AI]
category: "ComfyUI"
draft: true
lang: ""
---

## ComfyUI Desktop 소개

ComfyUI Desktop은 [ComfyUI](https://github.com/comfyanonymous/ComfyUI)를 하나의 응용 프로그램 형태로 만든 버전입니다.

깃허브 주소: <https://github.com/Comfy-Org/desktop>

- 장점

  - 설치가 매우 간편합니다. (파이썬 + 종속성 패키지 자동 설치)
  - **한글화**와 **ComfyUI-Manager**를 기본적으로 지원합니다.
  - [AUTOMATIC1111 WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)보다 최적화가 뛰어납니다.
  - 노드 기반 에디터로 다양한 커스터마이징이 가능합니다.
  - 안정 릴리스가 출시되면 자동으로 업데이트됩니다.

- 단점

  - 아직 베타 버전 단계라 버그가 많고 불안정합니다.
  - [AUTOMATIC1111 WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)보다 더 높은 학습 곡선이 필요합니다.

---

## 다운로드

설치 시 약 15GB의 저장 공간이 필요합니다.

- Windows (NVIDIA) x64: [다운로드](https://download.comfy.org/windows/nsis/x64)
- macOS ARM: [다운로드](https://download.comfy.org/mac/dmg/arm64)

---

## 재설치 오류 해결

`ComfyUI Desktop`을 설치한 적이 있으면, 기존 버전을 제거하고 다시 설치하려고 할 때 다음과 같은 오류가 발생할 수 있습니다.

![설치 오류 메시지](https://i.ibb.co/VCXVsky/2025-01-08-224039.png)

이 문제는 이미 개발팀이 인지하고 있으며, 다음 릴리스에서 패치될 예정입니다: <https://github.com/Comfy-Org/desktop/issues/592>

해결 방법은 `윈도우 + R` 키를 눌러 실행 창을 열고 `%APPDATA%`를 입력한 후 엔터를 누릅니다. 그러면 해당 위치로 탐색기가 열리고, 여기서 `ComfyUI` 폴더를 찾아 삭제한 후, `ComfyUI Desktop`을 다시 설치하면 정상적으로 설치할 수 있습니다.

---

## 설치 과정 설명

![1](https://i.ibb.co/ZHhsfXM/001.png)

시작하기를 클릭하세요.

---

![2](https://i.ibb.co/S7x0g3P/002.png)

다음을 클릭하세요.

---

![3](https://i.ibb.co/C9VCmVV/003.png)

설치 위치를 선택하고 다음을 클릭하세요.

---

![4](https://i.ibb.co/g9JdkV7/004.png)

기존에 설치된 ComfyUI가 있을 경우, 마이그레이션하거나 건너뛰고 다음을 클릭하세요.

---

![5](https://i.ibb.co/2st2nR0/005.png)

데스크탑 앱 설정을 원하는 대로 선택하거나 해제한 후 설치를 클릭하세요.

---

![6](https://i.ibb.co/D7fp1QL/006.png)

그러면 자동으로 파이썬 환경 설정이 시작되며, 완료되면 ComfyUI 서버가 실행됩니다.

---

![7](https://i.ibb.co/QCYvnYG/008.png)

잠시 기다리면 ComfyUI가 실행됩니다.

---

## 폴더 접근 바로가기

도움말 메뉴에서 모델, 로그 등 여러 폴더를 손쉽게 열 수 있습니다.

![8](https://i.ibb.co/mJkkvQv/009.png)

---

## 글 작성에 참고한 문서

<https://github.com/Comfy-Org/desktop>

<https://comfyorg.notion.site>

---

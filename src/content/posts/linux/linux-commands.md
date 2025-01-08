---
title: linux-commands
published: 2024-11-22
description: ""
image: ""
tags: []
category: "Linux"
draft: false
lang: ""
---

## **1. 파일 및 디렉토리 관리**

- `ls`: 디렉토리 내 파일 및 폴더 목록 표시

  - 옵션: `-l` (상세 정보), `-a` (숨김 파일 포함), `-h` (사람이 읽기 쉬운 형식)
  - 예: `ls -alh`

- `cd`: 디렉토리 이동

  - 예: `cd /home/user`

- `pwd`: 현재 작업 디렉토리 표시

  - 예: `pwd`

- `mkdir`: 새 디렉토리 생성

  - 예: `mkdir my_folder`

- `rm`: 파일 또는 디렉토리 삭제

  - 옵션: `-r` (디렉토리 및 하위 내용 삭제), `-f` (강제 삭제)
  - 예: `rm -rf folder_name`

- `cp`: 파일 또는 디렉토리 복사

  - 예: `cp file1.txt /destination/folder/`

- `mv`: 파일 또는 디렉토리 이동/이름 변경

  - 예: `mv old_name.txt new_name.txt`

- `touch`: 빈 파일 생성 또는 파일의 시간 정보 업데이트
  - 예: `touch newfile.txt`

---

## **2. 파일 내용 확인 및 편집**

- `cat`: 파일 내용 표시

  - 예: `cat file.txt`

- `less`: 파일을 한 화면씩 스크롤하며 읽기

  - 예: `less file.txt`

- `head`: 파일의 첫 몇 줄 확인

  - 예: `head -n 10 file.txt`

- `tail`: 파일의 마지막 몇 줄 확인 (로그 모니터링에 자주 사용)

  - 옵션: `-f` (실시간 업데이트)
  - 예: `tail -f log.txt`

- `nano`, `vim`: 파일 편집기
  - 예: `nano file.txt` 또는 `vim file.txt`

---

## **3. 프로세스 및 시스템 관리**

- `ps`: 현재 실행 중인 프로세스 확인

  - 옵션: `aux` (모든 사용자 및 세부 정보 표시)
  - 예: `ps aux`

- `top` 또는 `htop`: 실시간 프로세스 모니터링

  - 예: `top`

- `kill`: 특정 프로세스 종료

  - 예: `kill -9 <PID>` (PID는 프로세스 ID)

- `df`: 파일 시스템 디스크 사용량 확인

  - 옵션: `-h` (사람이 읽기 쉬운 형식)
  - 예: `df -h`

- `du`: 디렉토리 및 파일의 디스크 사용량 확인

  - 예: `du -sh folder_name`

- `uptime`: 시스템 가동 시간 및 로드 평균 확인

  - 예: `uptime`

- `free`: 메모리 사용량 확인
  - 옵션: `-h` (사람이 읽기 쉬운 형식)
  - 예: `free -h`

---

## **4. 네트워크 및 연결 관리**

- `ping`: 네트워크 연결 상태 확인

  - 예: `ping google.com`

- `ifconfig` 또는 `ip addr`: 네트워크 인터페이스 정보 확인

  - 예: `ifconfig` (이전 버전) 또는 `ip addr`

- `curl` 및 `wget`: HTTP 요청 또는 파일 다운로드

  - 예: `curl https://example.com` 또는 `wget https://example.com/file.zip`

- `netstat`: 네트워크 연결 및 포트 상태 확인

  - 예: `netstat -tuln`

- `ss`: 네트워크 소켓 확인 (netstat 대체 명령어)
  - 예: `ss -tuln`

---

## **5. 사용자 및 권한 관리**

- `whoami`: 현재 사용자 확인

  - 예: `whoami`

- `id`: 현재 사용자 ID 및 그룹 확인

  - 예: `id`

- `chmod`: 파일 권한 변경

  - 예: `chmod 755 file.sh`

- `chown`: 파일 소유자 변경

  - 예: `chown user:group file.txt`

- `sudo`: 관리자 권한으로 명령 실행
  - 예: `sudo apt update`

---

## **6. 패키지 관리 (예: Ubuntu/Debian 기반)**

- `apt update`: 패키지 목록 업데이트

  - 예: `sudo apt update`

- `apt upgrade`: 설치된 패키지 업데이트

  - 예: `sudo apt upgrade`

- `apt install`: 새 패키지 설치

  - 예: `sudo apt install package_name`

- `apt remove`: 패키지 제거
  - 예: `sudo apt remove package_name`

---

## **7. 기타**

- `history`: 사용한 명령어 기록 보기

  - 예: `history`

- `alias`: 명령어 단축키 설정

  - 예: `alias ll='ls -al'`

- `echo`: 텍스트 출력 (스크립트 작성 시 유용)

  - 예: `echo "Hello, World!"`

- `man`: 명령어의 매뉴얼 페이지 확인    
  - 예: `man ls`

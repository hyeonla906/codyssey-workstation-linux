# 트러블슈팅 기록

## 문제 1. Docker 명령어 실행 오류

**문제 상황**

Ubuntu 컨테이너 안에서 Docker 명령어를 실행했는데 오류가 발생했다.

**오류 명령어**
```bash
docker images ubuntu
```

**오류 메시지**
```text
bash: docker: command not found
```

**원인**

Docker 컨테이너 안과 WSL Ubuntu 환경을 구분하지 못하지못하고 명령어입력

**해결**

1. `exit`로 컨테이너에서 나왔다.
2. WSL Ubuntu에서 `docker images ubuntu`를 다시 실행

**결과**

Ubuntu 이미지 목록이 정상적으로 출력확인.

**사진:** `screenshots/18-error-docker-context.png`

---

## 문제 2. 파일 경로 입력 오류

**문제 상황**

HTML 파일 이름을 잘못 입력해서 오류가 발생.

**오류 명령어**
```bash
cat app/indx.html
```

**오류 메시지**
```text
cat: app/indx.html: No such file or directory
```

**원인**

`index.html`을 `indx.html`로 잘못 입력했다.

**해결**

1. `ls app`으로 실제 파일 이름을 확인했다.
2. `cat app/index.html`로 다시 실행했다.


HTML 파일 내용이 정상적으로 출력되었다.

**사진:** `screenshots/19-error-path.png`
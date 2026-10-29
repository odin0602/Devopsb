# 7주차 - Docker Compose

## 오늘 배운 내용

- 컨테이너 역할 분리: 앱과 DB를 각 컨테이너로 분리, 재시작 시 데이터 소실 방지

- compose.yaml: 여러 컨테이너의 실행 구성을 한 번에 관리

- 컨테이너 네트워크: compose 내부 DNS를 통해 IP 대신 서비스 이름으로 통신

- 볼륨: 컨테이너가 삭제되어도 데이터를 유지하기 위해 컨테이너 밖에 생성하는 저장 공간

## 1. `docker compose ps` 실행 결과

```text
NAME                IMAGE            COMMAND                  SERVICE   CREATED          STATUS                    PORTS
guestbook-nginx-1   nginx:alpine     "/docker-entrypoint.…"   nginx     23 minutes ago   Up 23 minutes             0.0.0.0:8080->80/tcp, [::]:8080->80/tcp
guestbook-redis-1   redis:7-alpine   "docker-entrypoint.s…"   redis     23 minutes ago   Up 23 minutes (healthy)   6379/tcp
guestbook-web-1     guestbook-web    "python app.py"          web       23 minutes ago   Up 23 minutes (healthy)   5000/tcp
guestbook-web-2     guestbook-web    "python app.py"          web       9 minutes ago    Up 9 minutes (healthy)    5000/tcp
guestbook-web-3     guestbook-web    "python app.py"          web       9 minutes ago    Up 9 minutes (healthy)    5000/tcp
```

---

## 2. `down` 후 `up` vs `down -v` 후 `up` 차이 비교

- **`down`**: 컨테이너와 네트워크만 지움, 데이터는 남음

- **`down -v`**: 볼륨까지 지움, 데이터도 사라짐

---

## 3. `.env` 파일을 Git에 올리지 않는 이유

- 비밀번호 등 민감한 정보가 유출될 수 있음.
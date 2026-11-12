# Docker Compose 정리



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


- 비밀번호 등 민감한 정보가 털릴 수 있음.
# Prowler Custom 가이드 라인

<br>

## 1. Auth 인증 키 변경

<br>

### 1. openssl rand -base64 32
#### - AUTH_SECRET="N/c6mnaS5+SWq81+819OrzQZlmx1Vxtp/orjttJSmw8=" 수정하여 입력

<br>

### 2. openssl genrsa -out private.pem 2048
#### - DJANGO_TOKEN_SIGNING_KEY="" 에 pem 키 내용 전체 삽입

<br>

### 3. openssl rsa -in private.pem -pubout -out public.pem
#### - DJANGO_TOKEN_VERIFYING_KEY="" 에 pem 키 내용 전체 삽입

<br>

### 4.  openssl rand -base64 32
#### - DJANGO_SECRETS_ENCRYPTION_KEY="oE/ltOhp/n1TdbHjVmzcjDPLcLA41CVI/4Rk+UB5ESc=" 수정하여 입력

<br>
<br>

## 2. Docker Build 명령어

<br>

### 0. cd 해당 폴더 진입 후

### 1. Windows
#### docker compose -f docker-compose-dev.yml up -d

<br>

### 2. MAC M 시리즈
#### DOCKER_DEFAULT_PLATFORM=linux/amd64 docker compose -f docker-compose-dev.yml up -d

<br>

### 3. 재실행 시 컨테이너 내리기
#### docker compose -f docker-compose-dev.yml down

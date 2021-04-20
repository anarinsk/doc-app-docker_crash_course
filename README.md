# doc-app-docker_crash_course

거두 절미하고 사례부터 들이민다. 

+ 도커의 개념 
  + 원격 저장소에서 도커 이미지를 끌어와서 
  + 특정한 옵션 및 환경 변수와 함께 실행하고 
  + 실행 중인 도커는 그 내에 접근할 수 있다. 

+ 따라서 도커 명령어를 나는 다음과 같은 계열로 나누고자 한다. 
  + image 계열 
  + run 계열 
  + exec 계열 


## Image 

- `docker images`, `docker image ls`: 이미지 조회 
- `docker rmi <IMAGE>`: 이미지 삭제 

## Run 

- `docker ps`: 현재 돌고 있는 도커 콘테이너를 조회 
  - `ocker ps -a`: 정지된 콘테이너를 포함, 모든 콘테이너를 보여준다. 
- `docker stop <CONTAINER>`: 콘테이너 멈추기 
- `docker rm <CONTAINER>`: 콘테이너 지우기 

## Exec 

 - `docker exec` : `-i -t` (옵션) + `hello` (콘테이너) + `/bin/bash` 실행할 명령 

## Other 

- `docker system df`: 디스크 이용량 보기 
- `docker image prune -a`: 안 쓰는 이미지 정리 
- `docker container prune`: 안 쓰는 콘테이너 정리 

## Frequently 

```shell
docker kill $(docker ps -q) # Kill all containers 
docker rm $(docker ps -a -q) # Delete all stopped containers 
docker rmi $(docker images -q) # Delete all images 
docker exec -i -t <CONTAINER> /bin/bash
```

## Reference 

[extremely useful docker commands - CodeNotary](https://www.codenotary.com/blog/extremely-useful-docker-commands/)
[도커 주요 옵션](https://khj93.tistory.com/entry/Docker-Docker-option-%EB%AA%85%EB%A0%B9%EC%96%B4-%EB%AA%A9%EB%A1%9D)

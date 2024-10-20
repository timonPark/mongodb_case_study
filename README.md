# Mongodb_case_study
MongoDB 상황별 학습 및 실습에 대한 코드 정리 

## 참조
[MongoDB Replication](https://locrian-gerbil-117.notion.site/MongoDB-Replication-123fafab7c9280a7ac11c68bb73f308b?pvs=4)

## MongoDB 서버 및 환경정보
- 서버 OS: Amazonlinux
- MongoDB Version: 8.0

## 실습
### Docker Container로 MongodDB 3대 생성
```
cd mongodb_replica_set
docker-compose up --build -d 
```

### MongodDB Replica Set 설정 및 연결확인
```
# 27017 MongoDB 서버 접속
$ mongosh "mongodb://localhost:27017"

# Replica Set 설정 초기화
$ rs.initiate({
    _id: "rs1",
    members: [
        { _id: 0, host: "host.docker.internal:27017" },
        { _id: 1, host: "host.docker.internal:27018" },
        { _id: 2, host: "host.docker.internal:27019" },
    ],
});

# 연결 확인
$ rs.status();
```
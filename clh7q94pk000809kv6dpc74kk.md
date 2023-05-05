---
title: "23년 1월 두번째 뉴스레터"
datePublished: Wed May 03 2023 13:21:44 GMT+0000 (Coordinated Universal Time)
cuid: clh7q94pk000809kv6dpc74kk
slug: 23-1
tags: newsletter

---

### **고 언어에서 SQL을 다루는 방법**

여러분들은 각자 다른 데이터베이스에 접근할 때, [pgx](https://github.com/jackc/pgx)같은 라이브러리를 이용하시나요?  
고 언어에 내장되어 있는 [database/sql](https://pkg.go.dev/database/sql) 라이브러리를 사용하면 어떤 SQL 데이터베이스든 같은 경험을 할 수 있습니다.  
한번 체험해 볼까요?  
[How to Work with SQL Databases in Go | Better Stack Community](https://betterstack.com/community/guides/scaling-go/sql-databases-in-go/)

---

### **TPC-C 벤치마크를 정복한 분산 SQL 데이터베이스, OceanBase**

최근 TPC-C 벤치마크 테스트에서 알리바바의 [OceanBase](https://www.oceanbase.com/en)가 종합 1위를 탈환했습니다!  
OceanBase는 오픈소스로 공개된 분산 SQL 데이터베이스로 MySQL과 호환되는 것이 특징입니다.  
오라클을 뛰어넘은 데이터베이스를 한번 써보는 건 어떠신가요??  
[OceanBase Did Better than Any Other Database in the TPC-C Benchmark | by Alibaba Cloud | Medium](https://alibaba-cloud.medium.com/oceanbase-did-better-than-any-other-database-in-the-tpc-c-benchmark-b12f603f4110)

---

### **고 언어의 효율적인 레디스 클라이언트**

Centrifugo에서 redigo, go-redis, rueidis를 벤치마크하고 비교하여 가장 효율적인 레디스 라이브러리를 고르기 위한 여정을 기록 했습니다.  
지난 뉴스레터에서 rueidis에 대해 소개한 적이 있는데요?  
Centrifugo는 어떤 결과를 맞이 했고, 어떤 선택을 했을 지 한번 읽어 볼까요?  
[Improving Centrifugo Redis Engine throughput and allocation efficiency with Rueidis Go library | Centrifugo (](https://centrifugal.dev/blog/2022/12/20/improving-redis-engine-performance)[centrifugal.dev](http://centrifugal.dev)[)](https://centrifugal.dev/blog/2022/12/20/improving-redis-engine-performance)

---

### **AVX512를 사용하는 방법**

AVX512는 x86 아키텍처의 [Advanced Vector Extensions](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions) SIMD(여러 데이터를 동시에 연산하는 하나의 명령어) 입니다.  
Gorse는 오픈소스 툴을 이용해 이 AVX512를 go 어셈블리에 추가하는 작업을 블로그로 공개했습니다.  
1ms가 중요한 작업을 다루신다면 한번 읽어 보시는 게 어떨까요!?  
[How to Use AVX512 in Golang via C Compiler | Gorse](https://gorse.io/posts/avx512-in-golang.html)  

---

### **postgreSQL을 감싸는 기술, prest**

prest는 포스트그레를 한번 감싸서 RESTful API로 데이터베이스에 접근할 수 있게 해주는 프로젝트입니다.   
이 프로젝트가 안정적으로 유지보수될 수 있게 된다면, 포스트그레스를 백엔드로 쓰고 있는 많은 다른 프로젝트에서 유용하게 쓰일 수 있을 것같습니다.  
[prest/prest: PostgreSQL ➕ REST, low-code, simplify and accelerate development, ⚡ instant, realtime, high-performance on any Postgres application, existing or new (](https://github.com/prest/prest)[github.com](http://github.com)[)](https://github.com/prest/prest)

---

### **여러분들은 웹 프레임워크가 무엇이라고 생각하시나요?**

고에는 스프링, 장고같은 프레임워크는 존재하지 않습니다.  
하지만 모든걸 지원한다 해도 스벨트킷처럼 특정 구조를 강제하지 않는다면, 그건 라이브러리가 아닐까요?  
그래서 고 커뮤니티는 웹 프레임워크를 추천해달라하면 net/http를 추천하는 경향이 있는 것같습니다.  
하지만 이번에는 고에서 가장 대표적인 웹 프레임워크인 Fiber, Echo, gin과 goyabe라는 유용해 보이는 웹 프레임워크도 같이 소개하겠습니다.  
[Fiber (](https://gofiber.io/)[gofiber.io](http://gofiber.io)[)](https://gofiber.io/)   
[Echo - High performance, minimalist Go web framework (](https://echo.labstack.com/)[labstack.com](http://labstack.com)[)](https://echo.labstack.com/)  
[gin-gonic/gin: Gin is a HTTP web framework written in Go (Golang) (](https://github.com/gin-gonic/gin)[github.com](http://github.com)[)](https://github.com/gin-gonic/gin)  
[Goyave](https://goyave.dev/)

---

### **JSON의 대체제, protobuf와 flatbuffer**

대부분의 상황에서 데이터 직렬화는 json을 사용합니다.  
json은 타입이 정해져 있기 때문에, 언제 어느 상황에서도 자유롭게 쓸 수 있습니다.  
하지만 같은 키에 여러 타입의 데이터가 입력될 수 있으므로, 때때로 안정성을 헤칠 수 있습니다.  
또한 이러한 특성 때문에 json은 비교적 느린 직렬화 방법으로 지목됩니다.  
그래서 구글은 프로토버퍼와 플랫버퍼라는 스키마를 공유한 형태의 직렬화 도구를 만들었습니다.  
[Protocol Buffers  |  Google Developers](https://developers.google.com/protocol-buffers?hl=ko)  
[FlatBuffers: FlatBuffers (](https://google.github.io/flatbuffers/)[google.github.io](http://google.github.io)[)](https://google.github.io/flatbuffers/)

---

### **zero copy와 디펜던시가 필요없는 vstruct**

vstruct는 미리 직렬화될 버퍼의 길이를 파악하여 만든 후, 그 버퍼에 쓰는 방식으로 메모리 사용량을 최소화 하였습니다.  
그리고 프로토버퍼나 플랫버퍼와 달리 직렬화&역직렬화를 위해 별도의 의존성을 프로젝트에 추가할 필요가 없습니다.   
[lemon-mint/vstruct: Code Generation Based High Speed Data Serialization Tool (](https://github.com/lemon-mint/vstruct)[github.com](http://github.com)[)](https://github.com/lemon-mint/vstruct)

---

### **JSON으로도 충분히 빠른 TCP 기반 RPC 라이브러리**

arpc는 grpc처럼 http2같은 추가 레이어 없이 TCP 바로 위에 자체적인 프로토콜을 설계 및 구현하여 만든 매우 빠른 RPC 프로토콜입니다.  
JSON을 사용하여도 grpc와 동등한 성능을 내는 것으로도 알려진 arpc는 JSON 대신 프로토버퍼같은 더 빠른 직렬화 수단을 사용하게 되면 더 큰 차이를 내게 됩니다.  
grpc로 만족할 수 없을 때, 한번은 해볼만한 선택지가 아닐까요?  
[lesismal/arpc: More effective network communication, two-way calling, notify and broadcast supported. (](https://github.com/lesismal/arpc)[github.com](http://github.com)[)](https://github.com/lesismal/arpc)

---

### **게임 엔진을 활용한 GUI 라이브러리**

고 언어에는 [ebitengine](https://ebitengine.org/)이라는 게임 엔진이 있습니다.  
고 언어로 2D 게임을 만들기 위한 엔진으로 유니티로도 일반적인 앱을 만드는 시도가 있는 만큼 에비텐으로도 가능할 것입니다.  
그 아이디어를 실현한 라이브러리가 바로 furex입니다.  
furex는 에비텐을 베이스로 만들어지며 네이티브 UI가 아닌 만큼 차후에 flutter와 비교될 수 있는 GUI 라이브러리가 되길 기대합니다.  
[yohamta/furex: A minimal GUI framework built on top of Ebitengine that provides support for the Flex Layout Algorithm. (](https://github.com/yohamta/furex)[github.com](http://github.com)[)](https://github.com/yohamta/furex)
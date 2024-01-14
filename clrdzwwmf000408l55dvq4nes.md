---
title: "24년 1월 전반기 뉴스레터"
datePublished: Sun Jan 14 2024 21:15:51 GMT+0000 (Coordinated Universal Time)
cuid: clrdzwwmf000408l55dvq4nes
slug: 24-1
tags: newsletter

---

조금 늦었지만 2024년 새해 복 많이 받으세요!

## UDP 기반의 Message Queue?

일반적인 메시지 큐의 경우엔 메시지 전송에 대한 정합성과 연결성 때문에 TCP로 처리하는게 일반적입니다.

UDP 기반으로 처리하면 메시지가 유실되었을 때 처리가 어려워질텐데, 고로 구현한 케이스가 있어 가져왔습니다.

[fairymq/fairymq: fairyMQ is an open-source UDP based message queue software written in GO. (github.com)](https://github.com/fairymq/fairymq)

---

## 고로 미디어 플레이어 하나 만들어 보실 생각 있으신가요?

누군가가 libmpv를 바인딩 해놨는데 해보실?

[gen2brain/go-mpv: Go bindings for libmpv (github.com)](https://github.com/gen2brain/go-mpv)

---

## CloudWeGo가 직접 보여주는 MSA 서버 구현

CloudWeGo는 고를 좋아하는 기업이고, 고를 기반으로 한 MSA 프레임워크를 RPC, HTTP 기반으로 각 하나씩 2개 발표한 적이 있습니다.

kitex와 hertx인데 얼마 전 이 2개를 이용한 예시 아티클을 발표했으니 관심 있으면 살펴보셨으면 합니다.

[Mastering Golang Microservices - A Practical Guide: Embrace High-Performance with Kitex and Hertz | CloudWeGo](https://www.cloudwego.io/blog/2024/01/10/mastering-golang-microservices-a-practical-guide-embrace-high-performance-with-kitex-and-hertz/)

[cloudwego/kitex: Go RPC framework with high-performance and strong-extensibility for building micro-services. (github.com)](https://github.com/cloudwego/kitex)

[cloudwego/hertz: Go HTTP framework with high-performance and strong-extensibility for building micro-services. (github.com)](https://github.com/cloudwego/hertz)

---

## fasthttp로 로드밸런서를?

[aaydin-tr/divisor: A fast and easy-to-configure load balancer (github.com)](https://github.com/aaydin-tr/divisor)

---

## JSONNET을 아시나요?

yaml에서도 써보는 경험을 할 수 있을 지도 모르겠습니다?

[micah5/yamlx: YAML with conditionals, expressions and loops (github.com)](https://github.com/micah5/yamlx)

---

## 터미널에서 DB 데이터를 확인해야 한적 있지 않나요?

아직은 베타테스트라서 MySQL만 지원하지만, 인터페이스가 현대적인 데이터베이스 툴을 보는 것같습니다.

[jorgerojas26/lazysql: A cross-platform TUI database management tool written in Go. (github.com)](https://github.com/jorgerojas26/lazysql)

---

## Express like golang web framework

[jvcoutinho/lit: A simple, fast and expressive HTTP framework for Go. (github.com)](https://github.com/jvcoutinho/lit)

---

## 유닛 테스트 과정에서의 로그 남기는 방법

[Beginner's Guide to Unit Test Logging in Go (youtube.com)](https://www.youtube.com/watch?v=UVfXsyHaDGc)

---

## 동시성을 관리하는 좋은 아티클을 가져왔습니다

http 요청으로 이렇게 재밌는 아티클을 만들 수 있다니...

[Concurrent HTTP Requests in Golang: Best Practices and Techniques | by Rafet Topcu | Insider Engineering | Jan, 2024 | Medium](https://medium.com/insiderengineering/concurrent-http-requests-in-golang-best-practices-and-techniques-f667e5a19dea)

---

## 고의 동시성이 가지는 한계?

[Scaling Golang to 192 Cores with Heavy I/O · Jaz's Blog (jazco.dev)](https://jazco.dev/2024/01/10/golang-and-epoll/)

---

## 우리가 올바르게 한 것과 잘못한 것들에 대해

[command center: What We Got Right, What We Got Wrong](https://commandcenter.blogspot.com/2024/01/what-we-got-right-what-we-got-wrong.html?m=1)

---

## Go 1.22 변경점 살펴보기

인터렉티브한 콘솔을 제공하니 한번 쭉 돌려보면 바뀐 걸 쉽게 이해하실 수 있으실 것같습니다.

[Go 1.22: Interactive release notes (antonz.org)](https://antonz.org/go-1-22/)

---

## 효과적인 양방향 통신 프로토콜이 필요해요

웹소켓만이 아니라 다른 프로토콜도 가능한!

[Centrifugo – scalable real-time messaging server in a language-agnostic way. Set up once and forever. | Centrifugo (centrifugal.dev)](https://centrifugal.dev/)

[googollee/go-socket.io: socket.io library for golang, a realtime application framework. (github.com)](https://github.com/googollee/go-socket.io)

---

## cgo 바인딩 너무 귀찮은 일이에요, 그쵸?

자동으로 해주면 정말 좋을 텐데, 맞죠?

[xlab/c-for-go: Automatic C-Go Bindings Generator for Go Programming Language (github.com)](https://github.com/xlab/c-for-go)

---

## 부하 테스트를 위해선 툴의 성능도 중요하죠

그쵸...? 클라우드 환경에 필요한 여러가지 Load, Performance Test Tools이 있어요, 고로 짜여진!

[grafana/k6: A modern load testing tool, using Go and JavaScript - https://k6.io (github.com)](https://github.com/grafana/k6)

[ddosify/ddosify: Effortless Kubernetes Monitoring and Performance Testing. Available on CLI, Self-Hosted, and Cloud (github.com)](https://github.com/ddosify/ddosify)

[codesenberg/bombardier: Fast cross-platform HTTP benchmarking tool written in Go (github.com)](https://github.com/codesenberg/bombardier)

[fortio/fortio: Fortio load testing library, command line tool, advanced echo server and web UI in go (golang). Allows to specify a set query-per-second load and record latency histograms and other useful stats. (github.com)](https://github.com/fortio/fortio)

---

## 디스코드는 어떻게 저 트래픽을 소화하는가?

[How Discord Serves 15-Million Users on One Server (bytebytego.com)](https://blog.bytebytego.com/p/how-discord-serves-15-million-users?ref=dailydev)

---

## 자바스크립트 진영의 떠오르는 라이브러리들

[2023 JavaScript Rising Stars](https://risingstars.js.org/2023/en?ref=dailydev)

---

## 저희도 최신 리눅스 커널을 서버로 쓰고 싶어요

[Linux 6.8 Network Optimizations Can Boost TCP Performance For Many Concurrent Connections By ~40% - Phoronix](https://www.phoronix.com/news/Linux-6.8-Networking)

---

## 구글의 API 디자인 가이드

[API 디자인 가이드  |  Google Cloud](https://cloud.google.com/apis/design?hl=ko)

---

## TIOBE 2023년의 언어, C# 축하합니다.

조만간 자바를 넘어서는 경이를 볼 수 있을 지도 모르겠어요

[TIOBE Index - TIOBE](https://www.tiobe.com/tiobe-index/)
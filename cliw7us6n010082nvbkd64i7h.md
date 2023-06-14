---
title: "23년 6월 전반기 뉴스레터"
datePublished: Wed Jun 14 2023 21:20:39 GMT+0000 (Coordinated Universal Time)
cuid: cliw7us6n010082nvbkd64i7h
slug: 23-6
tags: newsletter

---

## P2P와 VPN에 관심 없으신가요?

Anywherelan은 tun/wintun 드라이버와 libp2p 라이브러리를 기반으로 동작하는 P2P 네트워크 위에 mesh VPN을 구현한 어플리케이션입니다.

mesh VPN 솔루션은 많이 존재하지만 고 언어와 오픈소스 스택들로 이루어져 있어, 활용할 방법이 많은 게 장점이라 생각합니다.

[anywherelan/awl: Securely connect your devices into a private network (](https://github.com/anywherelan/awl)[github.com](http://github.com)[)](https://github.com/anywherelan/awl)

---

## 오늘도 새로운 ORM이 추가됩니다.

뉴스레터를 쓰는 동안 2달에 한번 꼴로 ORM을 싣는 것같습니다.

이번에 소개드릴 ORM은 스키마를 먼저 작성하고, 그 기반으로 type-safe한 쿼리 코드를 생성해 주는 것이 특징입니다.

현재 다양한 타입과 쿼리를 제공하고, 트랜잭션도 지원하고 있으니 한번 시도해 보시는 건 어떤가요!?

[swiftcarrot/queryx: Schema-first and type-safe ORM for Golang (](https://github.com/swiftcarrot/queryx)[github.com](http://github.com)[)](https://github.com/swiftcarrot/queryx)

---

## 여러분은 인터페이스를 잘 쓰고 계신가요?

혹시 인터페이스를 반환하고 계시지는 않으신가요?

필요 이상으로 구체적인 인터페이스를 받기를 원하지는 않으신가요?

그러면 인터페이스에 대한 이 글을 읽어 보세요!

[Using interfaces in Go the right way |](https://mbinjamil.dev/writings/using-interfaces-in-go/) [mbinjamil.dev](http://mbinjamil.dev)

---

## 스케일링과 로드밸런싱 좀 해주세요...

여러분들은 여러분의 어플리케이션을 스케일링 해야하거나 로드밸런싱을 해야한다면, 어떻게 하시나요?

물론 K8S를 하시는 분들은 이미 다 방법을 찾아서 하고 계실 거라 생각합니다.

하지만 저같이 아직 K8S를 제대로 접하지 못한 사람들은 그런 것이 무리거든요.  
그런 우리들을 위한 어려운 가이드를 가져왔습니다!  
영어가 어렵더라구요.

[Replicating and Load Balancing Go Applications in Docker Containers with Consul and Fabio | by Matt Wiater | May, 2023 | Better Programming](https://betterprogramming.pub/replicating-and-load-balancing-go-applications-in-docker-containers-with-consul-and-fabio-3ec5eed15154)

[Replicating and Load Balancing Go Applications in Docker Containers with Consul and Fabio | by Matt Wiater | May, 2023 | Better Programming](https://betterprogramming.pub/replicating-and-load-balancing-go-applications-in-docker-containers-with-consul-and-fabio-3ec5eed15154)

---

## 전 자바를 좋아하는 데

많은 고퍼 분들은 자바를 싫어합니다.

프로젝트 구조에서도 `src`를 쓰기 싫어하죠.

하지만 많은 고퍼 분들이 여전히 자바처럼 고를 작성하는 것같습니다.  
재밌는 아티클을 가져왔으니 한번 읽어보고 자아성찰을 해볼까요?

[Go is Not Java - DEV Community](https://dev.to/jarrodhroberson/go-is-not-java-1bd8)

---

## 포인터를 좋아하시나요, 복사를 좋아하시나요?

저는 포인터를 좋아하는데요.  
큰 구조체를 전부 넘겨주는 것보다야 낫다고 생각했습니다.

하지만 이 글을 보니까, 또 큰 값이라고 해도 꼭 포인터를 옮기는 것이 꼭 값을 복사하는 것보다 좋은 성능을 보이는 건 아닌가 싶습니다.

[Go: Using pointers to reduce copies is premature optimization |](https://trinitroglycerin.github.io/2023/06/10/Go-Using-pointers-to-reduce-copies-is-premature-optimization/) [aredherring.tech](http://aredherring.tech) [(](https://trinitroglycerin.github.io/2023/06/10/Go-Using-pointers-to-reduce-copies-is-premature-optimization/)[trinitroglycerin.github.io](http://trinitroglycerin.github.io)[)](https://trinitroglycerin.github.io/2023/06/10/Go-Using-pointers-to-reduce-copies-is-premature-optimization/)

---

## 여러분들은 퍼즈 테스트를 잘 사용하고 계신가요?

퍼즈 테스트를 알고 나서부터 좋다고 생각만 하고, 해야지라고 생각만 했습니다.

그래서 그런지 벌써 어떻게 쓰나 까먹어 가더라구요.

그런 상황에 퍼즈 테스트에 대한 좋은 가이드를 발견했습니다!

같이 퍼즈 테스트를 익혀서 안정적인 서비스를 만들어 봐요!

[Writing a Go fuzz target — Bitfield Consulting](https://bitfieldconsulting.com/golang/fuzz-target)

---

## 데이터베이스의 발전 과정

저는 JSON 상하차 전문가지, DB에 대해서는 잘 모릅니다.

대략적인 종류만 알고 있는데요.  
그래도 어떤 이유로 인해 어떤 패러다임이 나오고, 어떻게 해당 디비가 구현되고 했던 히스토리가 있다면 쉽게 그 시장을 이해할 수 있을 거라 보입니다.

[The growing pains of database architecture (](https://www.figma.com/blog/how-figma-scaled-to-multiple-databases/)[figma.com](http://figma.com)[)](https://www.figma.com/blog/how-figma-scaled-to-multiple-databases/)

---

## 자연어 시간 처리..?

최소한의 규칙만 맞추면 자연어로 된 시간을 파싱해주는 라이브러리가 생겼습니다..!

아직 영어, 러시아어, 브라질 포르투갈어만 가능합니다만 그래도 매우 끌리는 라이브러리입니다.

한번 시도해 보고 한국어 기여 하실 분 계실까요?

[olebedev/when: A natural language date/time parser with pluggable rules (](https://github.com/olebedev/when)[github.com](http://github.com)[)](https://github.com/olebedev/when)

---

## DataGrip은 비싸고, DBeaver는 좀 그렇다면?

IDE도 JVM 기반과 웹 기반이 쌍벽을 이루는 마당에, DB 매니저라고 그러지 말란 법 없지 않습니까?

여기 일렉트론과 스벨트 기반의 DB 매니저를 가져왔습니다.

[dbgate/dbgate: Database manager for MySQL, PostgreSQL, SQL Server, MongoDB, SQLite and others. Runs under Windows, Linux, Mac or as web application (](https://github.com/dbgate/dbgate)[github.com](http://github.com)[)](https://github.com/dbgate/dbgate)

---

## 쓰레드 단위로 워커를 동작시킬 수 있을까?

`lotsa`는 정말 놀랍게도 고루틴이 아니라 쓰레드에 맞춰서 워커를 실행합니다.

근데 아마.. 쓰레드.. 그렇습니다..

[tidwall/lotsa: Simple Go library for executing lots of operations spread over any number of threads (](https://github.com/tidwall/lotsa)[github.com](http://github.com)[)](https://github.com/tidwall/lotsa)

---

## 고 언어에서 고성능 정규표현식을 추구하면 안 되는 걸까?

이전부터 고 언어의 정규표현식은 성능이 안 좋다고 평가 되었습니다.

그래서 꾸준히 조금이라도 더 좋은 정규표현식 라이브러리가 나왔습니다만, 널리 쓰이는 케이스를 아직 보진 못 했습니다.

하지만 이번에 소개드릴 `czinc/rec`는 코드 생성을 기반으로 정규표현식의 성능을 개선한 케이스입니다.

[Producing a Go scanner in 1,219 bytes of code (](https://modern-c.blogspot.com/2023/05/producing-go-scanner-in-1219-bytes-of.html?m=1)[modern-c.blogspot.com](http://modern-c.blogspot.com)[)](https://modern-c.blogspot.com/2023/05/producing-go-scanner-in-1219-bytes-of.html?m=1)

[rec command -](https://pkg.go.dev/modernc.org/rec) [modernc.org/rec](http://modernc.org/rec) [- Go Packages](https://pkg.go.dev/modernc.org/rec)

[cznic / rec · GitLab](https://gitlab.com/cznic/rec)
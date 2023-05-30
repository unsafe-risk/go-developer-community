---
title: "23년 5월 후반기 뉴스레터"
datePublished: Tue May 30 2023 21:20:39 GMT+0000 (Coordinated Universal Time)
cuid: clias90320bd0donv9m9x0a0z
slug: 23-5
tags: newsletter

---

## 제네릭을 활용한 환경 변수 라이브러리

기존에 많은 환경변수 라이브러리들은 구조체 태그를 이용했었습니다.  
당연하게도 구조체 태그를 이용하게 되면 성능은 조금 희생해도 사용성을 크게 높일 수 있습니다.  
단순히 `Marsh`, `Decode` 메서드 정도만 만들어 주면 되었으니까요.

하지만 구조체 태그는 메타 데이터라서 저처럼 코드 내에 작성해 두는 게 마음이 편한 사람에게 불안함을 남기기도 하죠.  
이번에 소개시켜드릴 라이브러리는 순수 제네릭 특성 상 조금 귀찮게 되어 있지만, 코드 상에서 모든 걸 처리할 수 있습니다.

[davidmdm/env (](https://github.com/davidmdm/env)[github.com](http://github.com)[)](https://github.com/davidmdm/env)

---

## 윈도우에서도 파일 쓰다듬기

개인적으로 윈도우에서 `touch`를 쓰지 못 하는 건 불편 사항 중 하나였습니다.  
`posix` 환경에서 `touch`로 자주 파일을 생성하곤 했으니까요.

미쳐 만들 생각은 못 했는데, 때 마침 누군가가 만들어 놓은 걸 발견했습니다!

[AlperAkca79/touch: touch command from Unix/Linux for Windows OS's (](https://github.com/AlperAkca79/touch)[github.com](http://github.com)[)](https://github.com/AlperAkca79/touch)

---

## 분노에 찬 벤치마크

간단한 설정만으로 자신이 만든 REST API의 한계를 측정해 보고 싶지 않으신가요?

`rage`는 간단하게 `yaml` 파일을 작성하여 요청을 조정하여 벤치마크 테스트를 수행합니다.

[EdwinWalela/rage: Minimalistic CLI Load Tester (](https://github.com/EdwinWalela/rage)[github.com](http://github.com)[)](https://github.com/EdwinWalela/rage)

---

## 인지 부하를 겪을 때

코드를 읽을 때, 이해가 어려우신가요?

프로젝트 구조가 너무 어려운 것같나요?

상사가 그것도 못 하냐고 갈구나요?

그 모든 것들이 사실 여러분들의 문제가 아닐지도 모릅니다!  
그리고 우리도 그렇게 되지 않도록 조심해야겠죠!

[zakirullin/cognitive-load: 🧠 Cognitive Load Developer's Handbook (](https://github.com/zakirullin/cognitive-load)[github.com](http://github.com)[)](https://github.com/zakirullin/cognitive-load)

---

## 클라우드 서비스가 너무 많아

GCP, AWS, Azure만 해도 3개의 SDK를 써야합니다.  
거기에 다른 서비스가 들어가면 더 많아지죠.

그럴 일은 잘 없지만, 여러 서비스의 파일 시스템을 사용하게 되면 작성해야할 코드 수는 늘어납니다.  
그런 상황을 대비해 하나의 코드 베이스로 여러 서비스에 접근할 수 있는 라이브러리가 있습니다.

[opensaucerer/bifrost: Rainbow bridge for shipping your files to any cloud storage service (](https://github.com/opensaucerer/bifrost)[github.com](http://github.com)[)](https://github.com/opensaucerer/bifrost)

---

## 드디어 고에도 io\_uring이!

드디어 고에도 `io_uring` 라이브러리가 생겼습니다!

기존의 `net` 이나 `net/http`에 비해 당연히 로우레벨이지만 어느정도 눈에 띄는 성능 향상을 기대해도 되지 않을까요!?

[pawelgaczynski/gain: Gain is a high-performance io\_uring networking framework written entirely in Go. (](https://github.com/pawelgaczynski/gain)[github.com](http://github.com)[)](https://github.com/pawelgaczynski/gain)

[Writing High-performance TCP Applications Using the Gain Web Framework | by Paweł Gaczyński | May, 2023 | Better Programming](https://betterprogramming.pub/an-introduction-to-gain-part-1-writing-high-performance-tcp-application-df5f7253e54a)

---

## 고 코드를 파이썬에서 실행하는 방법

`gopy`라는 패키지를 사용하여 고 코드를 파이썬에서 쓸 수 있게 컴파일 하여 동작 시킬 수 있습니다.

문제는 여전히 쟁쟁한 C++과 rust 코드들로 이루어진 파이썬 네이티브 라이브러리들에 대한 경쟁력이 있는 지는 잘 모르겠습니다.

[Using a Golang package in Python using Gopy | Last9](https://last9.io/blog/using-golang-package-in-python-using-gopy/)

[go-python/gopy: gopy generates a CPython extension module from a go package. (](https://github.com/go-python/gopy)[github.com](http://github.com)[)](https://github.com/go-python/gopy)

---

## 메모리를 줄여야 산다

고 언어에서 메모리 사용량은 항상 중요한 이슈입니다.

여전히 GC가 완벽하게 동작하는 것같지만, 무엇인가 모자란 부분이 있다는 걸 부정할 수는 없습니다.  
그래서 지속적으로 메모리 사용량을 줄이거나, GC를 컨트롤하는 어드바이스가 많이 나와 있습니다.

[Taming Go's Memory Usage — and Avoiding a Rust Rewrite - YouTube](https://www.youtube.com/watch?v=nJm8qq05Zm4)

---

## 바다괴수 데이터베이스 어떠신가요?

카산드라는 NoSQL 데이터베이스 중 와이드 칼럼 데이터베이스로 분류 됩니다.

기본적으로 클러스터링을 가정하고 나온 데이터베이스라서 확장하기 유용하고, 대용량 데이터를 관리하기 좋습니다.

하지만 카산드라의 성능에도 성이 차지 않는 개발자들이 기존에 카산드라를 구성하고 있던 자바 대신 C++로 재구성 하였습니다.

그 결과 카산드라에 비해 비약적으로 증가한 처리량과 수용량을 가지게 되었다고 합니다.

그리고 무엇보다 고 언어에 적용되는 드라이버가 매우 사용성이 좋으므로 한번쯤 해보시길 권장합니다!

[ScyllaDB | Monstrously Fast + Scalable NoSQL](https://www.scylladb.com/)

[NoSQL이란 무엇인가? 대량데이터 동시처리위한 DBMS 종류와 특징 | 인사이트리포트 | 삼성SDS (](https://www.samsungsds.com/kr/insights/1232564_4627.html)[samsungsds.com](http://samsungsds.com)[)](https://www.samsungsds.com/kr/insights/1232564_4627.html)

[\[ScyllaDB\] 소개 : 네이버 블로그 (](https://m.blog.naver.com/sssang97/223112135333)[naver.com](http://naver.com)[)](https://m.blog.naver.com/sssang97/223112135333)

[scylladb/gocql: Package gocql implements a fast and robust ScyllaDB client for the Go programming language. (](https://github.com/scylladb/gocql)[github.com](http://github.com)[)](https://github.com/scylladb/gocql)

[scylladb/scylla-go-driver: Experimental, high performance Scylla Driver, University of Warsaw students' project (](https://github.com/scylladb/scylla-go-driver)[github.com](http://github.com)[)](https://github.com/scylladb/scylla-go-driver)

[scylladb/gocqlx: All-In-One: CQL query builder, ORM and migration tool (](https://github.com/scylladb/gocqlx)[github.com](http://github.com)[)](https://github.com/scylladb/gocqlx)
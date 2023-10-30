---
title: "23년 10월 후반기 뉴스레터"
datePublished: Mon Oct 30 2023 21:15:09 GMT+0000 (Coordinated Universal Time)
cuid: clodef9ik000408mf1llq97j6
slug: 23-10-1
tags: newsletter

---

## SQL 템플릿이라고 한번 들어보셨습니까?

개인적으로 동적으로 특정 필드 및 조건을 거는 SQL 쿼리를 생성할 때, 문자열 버퍼나 문자열 이어 붙이기를 자주 쓰는 편입니다.

근데 그렇게 하면 SQL 쿼리가 고 로직에 포함되어, 보기 힘들어지는 단점이 존재하더라고요.

그래서 한 번씩은 SQL을 한번 래핑할 필요가 있다고 생각했습니다.

입력과 출력에 맞춰서 SQL을 생성할 수 있는 템플릿 라이브러리, 어떠신가요?

[VauntDev/tqla: mas sql templating (github.com)](https://github.com/vauntdev/tqla)

[Golang Dynamic SQL Templating (vaunt.dev)](https://blog.vaunt.dev/dynamic-sql-template-with-golang)

---

## 마이크로소프트에게 모든 걸 맡기기

하지만 azure function이 아쉽게도 고 언어를 위한 템플릿은 제공하지 않더군요.

Custom Handler로 동작했는데, func cli를 통해 생성하면 폴더 구분이 지저분해지는 단점이 존재하죠.

누군가가 잘 만들어준 툴이 나오길 기다리고 있었는데, 기대해볼 만한 게 나온 것 같습니다.

[KarlGW/azfunc: Module to assist with Azure Functions with Custom handlers and Go (github.com)](https://github.com/KarlGW/azfunc)

---

## 내부 이슈 처리를 위한 툴 하나 가져가시죠

answer라는 앱이 있습니다.

간단히 로그인하고, 질문을 올리고, 답변을 달 수 있으며, 도커를 통해 배포된 이미지를 가지고 쉽게 서비스할 수도 있죠.

사내 이슈 및 문의 처리를 위한 앱으로 간단하게 구현할 생각이라면 좋을 것같습니다.

[Apache Answer | Free Open-source Q&A Platform](https://answer.apache.org/)

[Answer Enters Apache Incubator | Answer](https://answer.apache.org/blog/2023/10/24/answer-enters-apache-incubator/)

---

## 파일 저장소 서버가 필요하지 않으신가요?

[Storage Box (kurdmake.com)](https://storagebox.kurdmake.com/)

[AlandSleman/StorageBox: A Simple File Storage Service (github.com)](https://github.com/AlandSleman/StorageBox)

---

## systemctl GUI 관리자

가끔 systemctl에 대해 전체적으로 보고 싶을 때가 있긴 합니다.

Go로 짜여진 systemctl GUI 툴 한번 어떠신가요?

[shakg/g-systemctl: graphical systemctl to manage services (github.com)](https://github.com/shakg/g-systemctl)

---

## 전서구

전서구 보내보신 적 있으신가요.

전 없습니다.

[Telegraph](https://telegra.ph/)

---

## 고에서 프론트 짜기...

좋은... 그 나쁘지 않은... 것 같습니다...

[EdmondTabaku/gophront: A frontend library for Go (github.com)](https://github.com/EdmondTabaku/gophront)

---

## 업그레이드 가능한 뮤텍스에 대한 아이디어

그런적 있지 않으신가요? Read Lock을 걸었는데, 바로 내려오는 다음에 Write Lock을 걸어야 하는 케이스 말이에요.

예를 들면 `map` 자료형에서 값을 추출했지만, 존재하지 않아서 바로 다음에 추가를 해야하는 상황이라면?

당연하게도 순간적으로 RLock을 해제하고 WLock을 건 후에, 다시 있는 지 확인한 후 값을 추가하게 되겠죠.

이 과정에서 RLock을 해제하고 WLock을 다시 걸지 않고, 업그레이드 하는 아이디어에 대한 아티클이 있습니다!

[Upgradable Read Write Lock for Go | Upstash Blog](https://upstash.com/blog/upgradable-rwlock-for-go)

---

## 구조체에 타입 태그하기

[Tag your Go Types | Tamir Bahar](https://tamir.dev/posts/go-tag-interfaces-venomous-dogs/)

---

## Terraform 잘 쓰고 계신가요?

전 최근에 azure에 사용하기 위해 테라폼을 공부하고 있습니다.

테라폼을 흥미롭게 보던 중, 때마침 컬리 팀에서 테라폼에 대해 우역곡절을 겪은 여행기를 작성해둔 걸 보았습니다.

여러분도 테라폼을 쓰신다면, 한 번쯤 컬리 팀의 회고를 읽어 보는 건 어떨까요?

[DevOps팀의 Terraform 모험 - 컬리 기술 블로그 (kurly.com)](https://helloworld.kurly.com/blog/terraform-adventure/)

---

## C에서 GC를 쓸 수 있는 라이브러리

그러면 D 언어랑 뭐가 다르냐구요? 글쎄요.

[ivmai/bdwgc: The Boehm-Demers-Weiser conservative C/C++ Garbage Collector (bdwgc, also known as bow-gc, boehm-gc, libgc) (github.com)](https://github.com/ivmai/bdwgc)

---

## 리액트에서 C를 쓸 수 있는 라이브러리

굳이 왜 그러냐구요? 저도 잘 모르겠습니다.

[elnardu/react-use-c: Use C in your React! (github.com)](https://github.com/elnardu/react-use-c)

---

## 고 언어 내부 스케쥴링 라이브러리

크론탭과 비슷한 형태로 앱 내에서 스케쥴링을 할 수 있는 라이브러리입니다.

주기적으로 실행해야할 작업이 있어야 한다면, 좋은 선택지라 생각합니다.

[reugn/go-quartz: Minimalist and zero-dependency scheduling library for Go (github.com)](https://github.com/reugn/go-quartz)

---

## 날짜를 표현하는 여러가지 방법

RFC 3339, ISO 8601, HTML...

여러가지 표준이 있는데, 표준 내에 속한 여러가지 포맷을 보기 좋게 보여주는 사이트가 있습니다.

[RFC 3339 vs ISO 8601 vs HTML (ijmacd.github.io)](https://ijmacd.github.io/rfc3339-iso8601/)

---

## 레-레-레-레-레이디오!

전 세계의 라디오 채널을 들어 보고 싶으신가요?

고 언어로 작성된 TUI 글로벌 라디오 앱입니다.

[Zi0P4tch0/RadioGoGo: 📻 Go-powered CLI to surf global radio waves via a sleek TUI. Tune in & let's Go 🚀! (github.com)](https://github.com/Zi0P4tch0/RadioGoGo)

---

## HTTP 커넥션 재활용하기

`http connection churn`이 정확히 어떤 말인지 어휘력이 부족해서 제대로 이해하지 못 했습니다만, 대략적으로 부제와 반대의 의미로 보입니다.

[HTTP Connection churn in GO - DEV Community](https://dev.to/gkampitakis/http-connection-churn-in-go-34pl)

---

## 좀 더 똑똑하게 작업하기!

[⚡⚡ 7 Open Source Repositories That Will Make You 90% Smarter 😎 - DEV Community](https://dev.to/nathan_tarbert/7-repositories-that-will-make-you-90-smarter-2jb3?ref=dailydev)

---

## 멀지 않은 quic와 http3 도입

고 언어의 기본 라이브러리에는 http는 물론이고, http2도 있습니다.

그리고 quic와 http3에 대한 요구는 계속 있어왔습니다.

이제 quic 코드가 상당히 작성되어 있어, 곧 볼 수 있을 것같은 전망입니다.

[quic package - golang.org/x/net/internal/quic - Go Packages](https://pkg.go.dev/golang.org/x/net/internal/quic)

---

## 이거 왜 벌써...?

이전에 http server routing에 대한 프로포절이 올라간 적이 있습니다.

기본 http mux에서 고릴라 먹스나 httprouter 라이브러리같은 고급 라우팅 기능을 넣겠다는 거였죠.

근데 그 기능이 다음 릴리즈 버전인 1.22에 추가될 전망이라 합니다.

[Better HTTP server routing in Go 1.22 - Eli Bendersky's website (thegreenplace.net)](https://eli.thegreenplace.net/2023/better-http-server-routing-in-go-122/)

---

## 도커 없이 이미지 빌드하기

도커 데스크탑이 부분 무료로 바뀌면서 어쩌면 윈도 개발 환경에 도커 데스크탑을 쓰지 못하는 환경이 있을 수 있다고 생각됩니다.

그때 만약 내가 이미지로 만들어서 배포를 해야 한다면, 상당히 많은 자료가 도커로 작성되어 있는 인터넷 환경이 어려울 수 있을 것같습니다.

[Docker Images Without Docker - A Practical Guide (codefresh.io)](https://codefresh.io/blog/docker-images-without-docker-practical-guide/)

---

## 분산 시스템에서 데이터베이스 설계하기

[Designing Databases for Distributed Systems - DZone](https://dzone.com/articles/designing-databases-for-distributed-systems?ref=dailydev)
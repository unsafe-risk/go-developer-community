---
title: "23년 11월 전반기 뉴스레터"
datePublished: Tue Nov 14 2023 21:15:09 GMT+0000 (Coordinated Universal Time)
cuid: cloyu11kw000308l8bgv86h1k
slug: 23-11
tags: newsletter

---

## JSON으로 로컬 스토리지를 쓰겠다고?

간단히 설정 파일 저장 용으로 괜찮을 것 같은데, 그 정도면 사실 이런걸 써야할까 싶기도 해요?

[0x3alex/gorage: a simple local json based storage system written in go (](https://github.com/0x3alex/Gorage)[github.com](http://github.com)[)](https://github.com/0x3alex/Gorage)

---

## 혹시 in memory 펍섭 큐가 필요하지 않으신가요?

직접 만드는 것도 좋은 선택이지만, 시간이 부족하시다면 이런걸 쓰시는 것도 좋아 보입니다.

[pubsub/pubsub.go at main · WillYingling/pubsub (](https://github.com/WillYingling/pubsub/blob/main/pubsub.go)[github.com](http://github.com)[)](https://github.com/WillYingling/pubsub/blob/main/pubsub.go)

---

## 여러분은 sync 패키지에 대해 얼마나 알고 계신가요?

`mutex`, `rwmutex`, `pool`, `cond` 등에 대해 고를 좀 하신 분들은 어떻게 쓰는 지 다들 아실테지만, 고를 시작한지 얼마 안되신 분들에겐 좋은 글이 될 것같습니다.

[6 Key Concepts You Should Know for Concurrency in the Sync Package (](https://blog.devtrovert.com/p/go-sync-package-6-key-concepts-for)[devtrovert.com](http://devtrovert.com)[)](https://blog.devtrovert.com/p/go-sync-package-6-key-concepts-for)

---

## 사실 또 sync 패키지를 쉽게 쓸 수 있는 라이브러리가 있거든요.

[carlmjohnson/flowmatic: Structured concurrency made easy (](https://github.com/carlmjohnson/flowmatic/tree/main)[github.com](http://github.com)[)](https://github.com/carlmjohnson/flowmatic/tree/main)

---

## 트리로 만들어드림!

폴더 구조? 오브젝트 스토리지 계층? 마크다운 인덱스? 모든지 트리로 일단은 만들어 드립니다.

[ddddddO/gtree: Using either Markdown or Programmatically to generate trees🌳 and directories📁, and to verify directories🔍. Provide CLI, Golang library and Web. (](https://github.com/ddddddO/gtree#walkprogrammably-func)[github.com](http://github.com)[)](https://github.com/ddddddO/gtree#walkprogrammably-func)

---

## 테라폼 엔터프라이즈의 오픈소스 버전

[leg100/otf: An open source alternative to terraform enterprise. (](https://github.com/leg100/otf)[github.com](http://github.com)[)](https://github.com/leg100/otf)

---

## 당신의 데이터베이스 지식은 쓸모 있는 지식입니까?

라고 저자가 묻네요.

[Your database skills are not 'good to have' (](https://renegadeotter.com/2023/11/12/your-database-skills-are-not-good-to-have.html?ref=dailydev)[renegadeotter.com](http://renegadeotter.com)[)](https://renegadeotter.com/2023/11/12/your-database-skills-are-not-good-to-have.html?ref=dailydev)

---

## 감정은 개발에 중요한가요?

개발자의 감정 상태도 감히 비기능적 요소에 들어갈까요?

[Emotion-driven development - DEV Community](https://dev.to/ingosteinke/emotion-driven-development-4ai1?ref=dailydev)

---

## 여러분, 제발 고 모듈을 써주세요!

몇몇 강의들에서 고 모듈을 쓰지 않고, `GOPATH`를 수정해서 쓰는 것 같아요.

하지만 고는 1.11부터는 모듈이라는 기능을 쓰는 언어라는 걸 명심해주세요.

[Using Go Modules - The Go Programming Language](https://go.dev/blog/using-go-modules)

---

## nodejs 앱을 CI/CD 태우기

`npm install`과 `npm ci`의 차이에 대해 아시나요?

[Stop using “npm install” in your CI/CD pipeline | Robert Maier-Silldorff | Bits and Pieces | Bits and Pieces (](https://blog.bitsrc.io/stop-using-npm-install-in-your-ci-cd-pipeline-ba0378bbebfb)[bitsrc.io](http://bitsrc.io)[)](https://blog.bitsrc.io/stop-using-npm-install-in-your-ci-cd-pipeline-ba0378bbebfb)

---

## 데이터베이스 마이그레이션을 어떻게 하시나요?

전 툴을 쓰는 게 아직 좀 불안합니다만, 잘만 쓴다면 쉽고 빠르게 이주시킬 수 있을 것 같습니다.

[pressly/goose: A database migration tool. Supports SQL migrations and Go functions. (](https://github.com/pressly/goose)[github.com](http://github.com)[)](https://github.com/pressly/goose)

---

## golang 14주년 기념사(?)

[Fourteen Years of Go - The Go Programming Language](https://go.dev/blog/14years)

---

## 새로운 JSON 파서

[How to parse JSON using shift-reduce parsing approach (](https://rhaeguard.github.io/posts/json-parsing-shift-reduce/)[rhaeguard.github.io](http://rhaeguard.github.io)[)](https://rhaeguard.github.io/posts/json-parsing-shift-reduce/)

[rhaeguard/gojson: Yet Another JSON Parser, but parsed using bottom-up parsing technique for educational purposes (](https://github.com/rhaeguard/gojson)[github.com](http://github.com)[)](https://github.com/rhaeguard/gojson)

---

## 효과적인 문자열 관리 기법

`interning`의 가장 적절한 번역은 무엇일까요?

[Performance optimization techniques in time series databases: strings interning (](https://victoriametrics.com/blog/tsdb-performance-techniques-strings-interning/)[victoriametrics.com](http://victoriametrics.com)[)](https://victoriametrics.com/blog/tsdb-performance-techniques-strings-interning/)

---

## protobuf와 gRPC에 대한 문서 생성기

REST API(open api)엔 스웨거라는 게 존재합니다. 하지만 아쉽게도 gRPC에는 그런게 없었죠.

조금 투박하긴 하지만 이 툴이 아쉬움을 조금 덜어줄 수 있을 것입니다.

[ScaleableWebWorks/grpcdoc: cli to generate comprehensive html documentation for grpc/protobuf (](https://github.com/ScaleableWebWorks/grpcdoc)[github.com](http://github.com)[)](https://github.com/ScaleableWebWorks/grpcdoc)

---

## SQL이 실행되는 순서에 대해 잘 아시나요?

이 유튜브 영상이 그 순서를 알려주고, 그로 인해 어떻게 실행되어야 성능에 좋은지 생각할 수 있게 해주실 것입니다.

[Secret To Optimizing SQL Queries - Understand The SQL Execution Order - YouTube](https://www.youtube.com/watch?v=BHwzDmr6d7s)

---

## 요즘 터미널을 자꾸 IDE로 만드시는 분들이 많습니다.

매우 좋은 흐름인 것같구요. 마이크로소프트도 이 대열에 합류해서 매우 반갑습니다.

[microsoft/inshellisense: IDE style command line auto complete (](https://github.com/microsoft/inshellisense)[github.com](http://github.com)[)](https://github.com/microsoft/inshellisense)

---

## 스벨트.. 플로우..?

[https://svelteflow.dev/](https://svelteflow.dev/)

---

## 드디어 pure go 러닝 머신 라이브러리!

[nlpodyssey/spago: Self-contained Machine Learning and Natural Language Processing library in Go (](https://github.com/nlpodyssey/spago)[github.com](http://github.com)[)](https://github.com/nlpodyssey/spago)

---

## 고 언어로 짜여진 허니팟 프레임워크

[Home - Beelzebub Blog (](https://beelzebub-honeypot.com/)[beelzebub-honeypot.com](http://beelzebub-honeypot.com)[)](https://beelzebub-honeypot.com/)

---

## postgresql을 이용한 스트리밍 플랫폼 제작기

포스트그레로...? 나츠처럼...?

[Building a Streaming Platform in Go for Postgres (](https://blog.peerdb.io/building-a-streaming-platform-in-go-for-postgres)[peerdb.io](http://peerdb.io)[)](https://blog.peerdb.io/building-a-streaming-platform-in-go-for-postgres)
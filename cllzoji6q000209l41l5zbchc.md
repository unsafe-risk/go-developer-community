---
title: "23년 8월 후반기 뉴스레터"
datePublished: Thu Aug 31 2023 21:30:12 GMT+0000 (Coordinated Universal Time)
cuid: cllzoji6q000209l41l5zbchc
slug: 23-8-1
tags: newsletter

---

## 쉬운 국제화 라이브러리

i18n에 곤란했던 적 있으신가요?

전 아직 i18n을 고려할 만한 프로젝트를 해보지 않아서 고려해본 기억도 없습니다.

하지만 하게 된다면, 저라면 맵을 통해 구현하지 않을까 생각해요.

이런 라이브러리처럼 래핑도 되어 있다면 더 좋겠네요.

[eduardolat/goeasyi18n: 🌍🚀 Effortlessly simple i18n for Go. Plurals, gender, and more made easy! (](https://github.com/eduardolat/goeasyi18n)[github.com](http://github.com)[)](https://github.com/eduardolat/goeasyi18n)

---

## 고로 만들어진 간단한 협업 툴

여러분들은 고로 처음 만들어본 프로젝트가 무엇인가요?

저는 졸업 과제로 해본 온라인 투표 시스템이었던 것같아요.

이 프로젝트는 간단한 보드 협업 툴인데, 무려 첫 프로젝트라고 합니다.

개발자의 최소가 이정도라니, 좀 쩌네요.

[Wave-95/boards: Live collaboration tool built with Go backend and Next.js, Typescript, & Tailwind frontend (](https://github.com/Wave-95/boards)[github.com](http://github.com)[)](https://github.com/Wave-95/boards)

---

## 고로 채팅 서버 만들어 보시겠습니까?

전 좀 그렇네요.

[iammuho/NatterNet: Your real-time chat application built with Golang, MongoDB, WebSockets, and Fasthttp. (](https://github.com/iammuho/NatterNet)[github.com](http://github.com)[)](https://github.com/iammuho/NatterNet)

---

## slog에 로그 발생 위치 남기기

zap이나 zerolog를 보면 로그가 발생한 위치를 남길 수 있는 옵션이 제공됩니다.

하지만 slog는 기본적으로 제공하는 것은 없죠.

하지만 당연히 `runtime` 패키지를 통해 구할 수 있음을 알고 계실 겁니다.

그걸 좀 더 쉽게 해볼까요?

[Display the source code reference that’s writing a log message | Stackademic](https://blog.stackademic.com/display-the-source-code-reference-writing-a-log-message-dc660b758b3e)

---

## 다들 gRPC, 어떻게 관리하시나요?

코드 생성이 필요한 디펜던시를 어떻게 관리하느냐도 중요한 이슈인 것같습니다.

지금 소개할 아티클은 프로토버퍼와 gRPC 코드와 관련된 건데요.

개인적으로 선호하는 방식은 아니지만, 배울 부분이 많다고 생각합니다.

[Organize gRPC and protobuf code in Golang (](https://rkiselenko.dev/blog/grpc-in-golang/)[rkiselenko.dev](http://rkiselenko.dev)[)](https://rkiselenko.dev/blog/grpc-in-golang/)

---

## 저는.. json에..

굳이 맵을 쓰고 싶진 않습니다..

[chenhg5/jsonmap: jsonmap: map the enum value to human-readable text defined in the struct tag when doing json marshal and unmarshal operations (](https://github.com/chenhg5/jsonmap)[github.com](http://github.com)[)](https://github.com/chenhg5/jsonmap)

---

## 컨텍스트 잘 쓰고 계신가요?

go 1.21에 새로운 기능도 추가되고, 지속적으로 사용법에 대한 아티클이 나오고 있습니다.

아직 컨텍스트를 안 쓰거나, 잘 모르신다면 다음 두 아티클을 보시는 건 어떠신가요?

[Context 패키지 (실전) | snowmerak](https://snowmerak.pages.dev/posts/019_context_ex/)

[How to propagate context without cancellation - Tyk API Gateway](https://tyk.io/blog/how-to-propagate-context-without-cancellation/)

---

## API 요청을 JSON으로 받는데요?

자동으로 객체로 만들어 받고 싶습니다.

[How to create a generic JSON request function, over HTTP, in Go? (](https://cristiancurteanu.digitalpress.blog/how-to-create-a-generic-http-request-function-in-go/)[digitalpress.blog](http://digitalpress.blog)[)](https://cristiancurteanu.digitalpress.blog/how-to-create-a-generic-http-request-function-in-go/)

---

## 마이크로소프트에게 모든 걸 맡기기

마이크로소프트에게 고를 배우면 더 잘해지지 않을까요?

[Take your first steps with Go - Training | Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/go-first-steps/)

---

## 실시간 노티피케이션 서비스 만들기 with kafka

이벤트가 지속적으로 발생하는 서비스는 언제나 설레죠.

데이터가 지속적으로 들어오고, 흐르고, 처리되는 걸 보면 기분이 좋습니다.

그리고 그 과정에 최소 메시지 큐는 높은 확률로 들어가게 되죠.

우리에겐 NATS라는 선택지가 존재하지만, 대규모에 안정성을 위한 선택지로 카프카를 선택했을 때의 경험을 한번 구경해볼까요?

[How to Build a Real-Time Notification System with Go and Kafka (](https://www.freecodecamp.org/news/build-a-real-time-notification-system-with-go-and-kafka/)[freecodecamp.org](http://freecodecamp.org)[)](https://www.freecodecamp.org/news/build-a-real-time-notification-system-with-go-and-kafka/)

---

## io\_uring 풀포트!

io\_uring은 리눅스의 IO 처리 모델 중 하나입니다.

비교적 최근에 등장했고, 2개의 링버퍼를 사용하는 것이 특징입니다.

기존 모델들에 비해 성능 향상이 있다고 알려져 있는데, 어느 정도인지 한번 확인해 볼까요?

[pawelgaczynski/giouring: Go programming language port of liburing. (](https://github.com/pawelgaczynski/giouring)[github.com](http://github.com)[)](https://github.com/pawelgaczynski/giouring)

---

## 고 위에서 돌아가는 JVM

그러나 JNI는 없는 JVM입니다.

java 17을 기준으로 구현 중이니 완성되면 여러가지 실험적인 프로젝트를 할 수 있어 보입니다.

[platypusguy/jacobin: A more than minimal JVM written in Go and capable of running Java 17 classes. (](https://github.com/platypusguy/jacobin)[github.com](http://github.com)[)](https://github.com/platypusguy/jacobin)
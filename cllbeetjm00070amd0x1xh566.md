---
title: "23년 8월 전반기 뉴스레터"
datePublished: Mon Aug 14 2023 21:40:09 GMT+0000 (Coordinated Universal Time)
cuid: cllbeetjm00070amd0x1xh566
slug: 23-8
tags: newsletter

---

> 의도한건 아니지만 딱 8월 15일에 뉴스레터를 발간하게 되었습니다. 한국에선 의미 있는 날인만큼 저도 그렇고, 모두 순국선열 분들의 희생에 감사하며 평화로운 하루 보내시길 바랍니다.

---

## 저 고 처음 시작하는 데 뭘로 시작하면 되요?

라고 물으신다면 여러분에게는 이 레포가 필요할 것입니다.

기본적인 연산자들에서 제어문, 바이너리, 컬렉션들(이 있었어?), 비동기까지!

실행하며 배울 수 있는 테스트 코드가 작성되어 있는 `go_assessment`를 시도해보세요!

[dmh2000/go\_assessment: A port of Rebecca Murphey's js-assessment for Go (](https://github.com/dmh2000/go_assessment)[github.com](http://github.com)[)](https://github.com/dmh2000/go_assessment)

---

## CLI 툴 하나 더 필요 없습니까?

저는 `kingpin`을 주로 쓰고 있습니다.

아쉽게도 별 다른 선택지가 없었던게 컸죠. 코브라가 좋다지만 손에 안 익더라구요.

`lieut`는 앞서 제가 얘기한 라이브러리들에 비해 가벼운 걸 자랑으로 삼고, 그 덕에 충분히 어렵지 않을 것으로 생각됩니다.

[Rican7/lieut: An opinionated, feature-limited, no external dependency, "micro-framework" for building command line applications in Go. (](https://github.com/Rican7/lieut)[github.com](http://github.com)[)](https://github.com/Rican7/lieut)

---

## 패턴.. 매칭..?

뭔가 새로운 패턴매칭 라이브러리가 나타났습니다.

제네릭과 메서드 체인으로 나타나는 성능은 잘 모르겠지만, 코드 자체는 아름다운 라이브러리입니다.

[PhakornKiong/go-pattern: Pattern Matching library for go (](https://github.com/PhakornKiong/go-pattern)[github.com](http://github.com)[)](https://github.com/PhakornKiong/go-pattern)

---

## HTMX와 함께 하는 웹 게임 개발기

고 언어를 백엔드로, HTMX를 프론트 라이브러리로 활용하면 좋은 웹앱이 나올 거같다는 생각은 자주 합니다.

하지만 행동으로 옮기지는 못 하고 있었습니다.

확신이 없었거든요. 그럴 때 가장 좋은 게 간접 경험이죠.

한번 읽어 보고 고 템플릿 라이브러리와 HTMX로 어떻게 페이지를 만들고 데이터를 주고 받았는지 확인해 보세요!

[Building a Web Game with Go & htmx | by Abayomi Popoola | Aug, 2023 | Medium](https://medium.com/@abayomip/building-a-web-game-with-go-htmx-2c7fa637d923)

---

## 여러분은 비터비 인코딩이 뭔지 아십니까?

저는 몰랐습니다.

근데 말이죠. 아직 잘 모르겠습니다.

DP를 활용한 인코딩 알고리즘이고, 오류 검출에 유용하다. 대신 메모리 요구량이 높다.

그 정도 밖에 모르겠습니다.

잘 모르겠습니다. 하지만 매력적으로 보입니다.

[8ff/viterbi: Convolutional encoder and a Viterbi decoder written in Golang (](https://github.com/8ff/viterbi)[github.com](http://github.com)[)](https://github.com/8ff/viterbi)

---

## 컴파일 언어 in GO

`Expr`은 고 언어로 쓰여진 컴파일 언어입니다.

물론 패키지로써 임포트해서 쓸 수도 있죠.

강타입 언어고 고 언어와 비슷한 느낌도 많은 언어입니다.

지금 당장 쓸만한 임베딩 되는 언어를 원하시면 한번 시도해 보시는 건 어떤가요?

[Expr | Expression language (](https://expr.medv.io/)[medv.io](http://medv.io)[)](https://expr.medv.io/)

---

## 고 1.21 릴리즈로 바뀌는 것들

고 언어 1.21에 새로 추가된 기능도 많고 변경 사항도 많습니다.

그냥 쭉 보면 막막하니 정리된 문서 몇개를 동봉해 드리겠습니다.

[Go 1.21 All You Need to Know, Online Whiteboard for Visual Collaboration (](https://miro.com/app/board/uXjVMBkmPPQ=/)[miro.com](http://miro.com)[)](https://miro.com/app/board/uXjVMBkmPPQ=/)

[Understanding Go 1.21 generics type inference – Encore Blog](https://encore.dev/blog/go1.21-generics)

[What I worked on for Go 1.21 · The Ethically-Trained Programmer (](https://blog.carlmjohnson.net/post/2023/go-121-flag-boolfunc-constraints/)[carlmjohnson.net](http://carlmjohnson.net)[)](https://blog.carlmjohnson.net/post/2023/go-121-flag-boolfunc-constraints/)

---

## SQL 연결 끊어!

여러분들은 SQL 연결이나 pre statement, rows를 닫지 않아 과도한 트래픽이 유발된 적 없으신가요?

전 있습니다. 가상 네트워크 사용료가 좀 나왔었죠.

하지만 이제 그 걱정을 할 필요가 없어졌습니다.

새로운 린터를 발견했거든요.

[A linter I really recommend you to use if you’re doing SQL in Golang | by Piotr Jastrzebski | Aug, 2023 | Turso blog](https://blog.turso.tech/a-linter-i-really-recommend-you-to-use-if-youre-doing-sql-in-golang-ab9fcf5b561f)

---

## TypeChat을 아십니까?

마이크로소프트에서 Typescript 기반으로 나온 타입 기반 자연어 처리를 위한 라이브러리라고 생각하시면 좋을 것같습니다.

그 TypeChat의 고 포팅 라이브러리가 나왔습니다.

한번 타입 기반으로 뭔가를 해보실 분들은 해보셔도 좋지 않을까요?

[maiqingqiang/TypeChat-Go: 🤖 This is the Go language implementation of microsoft/TypeChat. ⭐️ Star to support our work~ (](https://github.com/maiqingqiang/TypeChat-Go)[github.com](http://github.com)[)](https://github.com/maiqingqiang/TypeChat-Go)

---

## GopherCon Korea 2023이 있었습니다.

근데 제가 7월 말 뉴스레터에 까먹고 싣지 않았죠.

아직 영상이나 자료가 공유된 걸로 보이진 않는데요?

스케치 영상과 유튜브 라이브 영상 풀버전은 남아 있으니, 고퍼콘을 가보지 않았고 편집 영상 나오기 전에 보고 싶으시다면 아래 남겨 드리는 링크를 보시는 것도 좋을 것같습니다.

2일차는 꼭 마지막까지 보시는 걸 추천합니다!

[https://youtu.be/ImaHdBHTWUY](https://youtu.be/ImaHdBHTWUY)

[https://www.youtube.com/live/WZthMW0BaNA?feature=share](https://www.youtube.com/live/WZthMW0BaNA?feature=share)

[https://www.youtube.com/live/8AUVKh0qJgU?feature=share](https://www.youtube.com/live/8AUVKh0qJgU?feature=share)

---

## 애저는 여러분들을 환영합니다.

[RIP AWS Go Lambda Runtime | Mark Wolfe's Blog](https://www.wolfe.id.au/2023/08/09/rip-aws-go-lambda-runtime/)

---

## 주니어가 되는 것을 그만두세요.

최근에 시니어와 주니어에 대해서 생각해봤습니다.

저는 직급은 주니어인데요.

과연 시니어와 주니어를 나누는 기준은 뭐고, 우린 어떻게 시니어가 될 수 있을까요?

[(번역) 주니어가 되는 것을 그만두세요. (](https://hellomooneekim.netlify.app/stop-being-a-junior/)[hellomooneekim.netlify.app](http://hellomooneekim.netlify.app)[)](https://hellomooneekim.netlify.app/stop-being-a-junior/)
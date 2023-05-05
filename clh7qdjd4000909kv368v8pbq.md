---
title: "23년 2월 첫번째 뉴스레터"
datePublished: Wed May 03 2023 13:25:10 GMT+0000 (Coordinated Universal Time)
cuid: clh7qdjd4000909kv368v8pbq
slug: news-23-03
tags: newsletter

---

### **여러분들은 고를 어떻게 공부하시나요?**

각자, 자신이 생각하는 이상적인 교재와 공부 방식이 있을 것입니다.  
하지만 지금 당장은 저의 추천 대로 다음 아티클과 블로그를 정독해 보는 건 어떨까요?  
절대 손해 보는 일은 없을 겁니다. 히히  
[Go Type System Overview -Go 101](https://go101.org/article/type-system-overview.html)  
[Go Style | styleguide (](https://google.github.io/styleguide/go/)[google.github.io](http://google.github.io)[)](https://google.github.io/styleguide/go/)  
["The Ultimate Go Study Guide" 한글 번역 프로젝트 - The Ultimate Go Study Guide (](https://ultimate-go-korean.gitbook.io/book/)[gitbook.io](http://gitbook.io)[)](https://ultimate-go-korean.gitbook.io/book/)  
[Gophercises - Coding exercises for budding gophers](https://gophercises.com/)

---

### **잠시 설문조사 나왔는데요?**

유용한 CLI 툴을 하나 소개해 드릴까 합니다.  
고랭에서 CLI 입력을 받을 때, 특정 타입에 대한 입력을 구현해야할 때가 있습니다.  
그럴 때 유용한 survey란 라이브러리는 일반 문자열, 멀티라인 문자열, 비밀번호, 확인(Y/N), 선택지 선택 등을 손쉽게 만들 수 있습니다!  
[go-survey/survey: A golang library for building interactive and accessible prompts with full support for windows and posix terminals. (](https://github.com/go-survey/survey)[github.com](http://github.com)[)](https://github.com/go-survey/survey)

---

### **손 쉽게 웹 서버 구현하기**

고랭의 가장 훌륭한 웹 프레임워크로 net/http를 많은 고퍼들이 뽑고 있습니다.  
실제로 그 자체로도 훌륭하게 웹 서버를 만들 수 있고, 강력한 기능을 제공합니다.  
하지만 일부 아쉬운 부분을 메꾸어 줄 라이브러리 몇개를 소개해 드리겠습니다.  
httprouter는 매우 가볍고 빠르며 라우터이며, path variable도 제공하는 라우터입니다.  
그리고 gobwas/ws는 가볍고 쉽게 붙일 수 있는 웹소켓 라이브러리입니다.  
두 라이브러리만 추가함으로 net/http만 사용했을 때보다 훨씬 쾌적한 생산성을 얻을 수 있을 것입니다.  
[julienschmidt/httprouter: A high performance HTTP request router that scales well (](https://github.com/julienschmidt/httprouter)[github.com](http://github.com)[)](https://github.com/julienschmidt/httprouter)  
[gobwas/ws: Tiny WebSocket library for Go. (](https://github.com/gobwas/ws)[github.com](http://github.com)[)](https://github.com/gobwas/ws)  
마지막으로 uRouter는 웹 프레임워크라고 할 수는 없지만, 단순한 라우터라곤 할 수 없을 정도로 다양한 기능을 제공합니다.  
net/http에서 멀어지는 선택지가 되겠지만, 이런 식의 웹 라이브러리도 한번 접해보시는 걸 추천합니다.  
[lxzan/uRouter: HTTP & WebSocket router library for golang (](https://github.com/lxzan/uRouter#websocket)[github.com](http://github.com)[)](https://github.com/lxzan/uRouter#websocket)

---

### **I'm fyne, thank you.**

fyne은 고에서 크로스 플랫폼 GUI 앱을 쉽게 빌드할 수 있는 몇 안되는 툴입니다.  
V2가 되고 UI도 꽤 미려해졌습니다.  
한가지 단점이라면, cgo를 쓴다는 건데 역시 어쩔 수 없겠죠?  
[fyne-io/fyne: Cross platform GUI in Go inspired by Material Design (](https://github.com/fyne-io/fyne)[github.com](http://github.com)[)](https://github.com/fyne-io/fyne)  
그리고 fyne 프로젝트는 fyne-x를 통해 기본 위젯보다 확장된 기능을 제공하고 있으니 참고 하시면 더 나은 UI를 구현하실 수 있을 것입니다.  
[fyne-io/fyne-x: Community extensions to the cross platform GUI in Go based on Material Design (](https://github.com/fyne-io/fyne-x)[github.com](http://github.com)[)](https://github.com/fyne-io/fyne-x)

---

### **로그를 남기는 방법들**

고랭에는 log 라이브러리를 통해 로그를 남기는 가장 간단한 방법이 있습니다.  
하지만 표준 라이브러리가 지원하는 수준이 해당 시간에 적절한 문구를 남기는 수준에 그치기 때문에 실 환경에 쓰기에 아쉬운 점이 있었습니다.  
그래서 다양한 로그 라이브러리들이 만들어졌고, 그 중 매력적인 로그 라이브러리들을 소개할까 합니다.  
zerolog는 힙얼록을 하지 않는 다고 하는 라이브러리입니다. 만약 여러분들의 프로젝트가 메모리 사용량이 많다면 고려해볼만한 옵션이라 생각합니다.  
[rs/zerolog: Zero Allocation JSON Logger (](https://github.com/rs/zerolog)[github.com](http://github.com)[)](https://github.com/rs/zerolog)  
logrus는 WithField와 WithFields 메서드를 통해 쉽게 로깅을 위한 데이터를 편하고 쉽게 추가할 수 있습니다.  
[sirupsen/logrus: Structured, pluggable logging for Go. (](https://github.com/sirupsen/logrus)[github.com](http://github.com)[)](https://github.com/sirupsen/logrus)  
zap은 우버가 만든 로그 라이브러리로 고랭의 로그 라이브러리 중에 가장 빠르다고 알려져 있습니다. 로깅 성능이 중요하다면 고려할만한 옵션이라 봅니다.  
[uber-go/zap: Blazing fast, structured, leveled logging in Go. (](https://github.com/uber-go/zap)[github.com](http://github.com)[)](https://github.com/uber-go/zap)
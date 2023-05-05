---
title: "23년 2월의 두번째 뉴스레터"
datePublished: Wed May 03 2023 13:31:13 GMT+0000 (Coordinated Universal Time)
cuid: clh7qlbb7000z09mf4btjalet
slug: news-23-04
tags: newsletter

---

### **아직은 실험적인 코드 생성 기반 빠른 직렬화 라이브러리**

lemon-mint님의 gobe는 아직은 개발 단계에 있지만, 코드 생성 기반의 직렬화/역직렬화를 제공합니다.  
실 프로젝트에 바로 도입하기에는 부담이 있을 수 있겠지만, 코드 제너레이트에 대해 공부하기에 좋은 프로젝트라고 생각합니다.  
[lemon-mint/gobe: GOBE: Go Binary Encoding (](https://github.com/lemon-mint/gobe)[github.com](http://github.com)[)](https://github.com/lemon-mint/gobe)

---

### **QUIC와 HTTP3를 구현한 라이브러리**

quic-go는 고 언어에서 현재는 지배적인 위치에 있는 QUIC 라이브러리입니다.  
간단한 설정으로 HTTP3로도 사용할 수 있게 작성할 수 있는 유용한 라이브러리입니다!  
한번 레이턴시가 중요한 서버는 QUIC를 통해 제공해 보는 건 어떨까요?  
[quic-go/quic-go: A QUIC implementation in pure go (](https://github.com/quic-go/quic-go)[github.com](http://github.com)[)](https://github.com/quic-go/quic-go)  

---

### **고에서 오픈텔레메트리를 사용하는 방법**

여러분들은 자체적인 APM 툴을 개발하고 적용한 적이 있으신가요?  
그때 다른 APM 툴과의 호환은 어떻게 보장 하셨었나요??  
오픈텔레메트리는 그 고민을 해결해줄 기술일 겁니다.  
그리고 Komu Wairagu는 고에서 오픈텔레메트리를 다루는 가이드를 자신의 블로그에 기고 했습니다.  
한번 따라가며 적용해봅시다!  
[The complete guide to OpenTelemetry in Golang. (](https://www.komu.engineer/blogs/11/opentelemetry-and-go)[komu.engineer](http://komu.engineer)[)](https://www.komu.engineer/blogs/11/opentelemetry-and-go)

---

### **귀여운 로그 라이브러리**

한번 쯤 로그를 귀엽고 예쁘게 남기고 싶지 않으신가요?  
charm은 단순히 귀엽고 예쁜 포맷으로 로그를 남기는 게 아닌 유용한 기능까지 제공해서 귀엽고 예쁘게 로그를 남겨 줍니다!  
사용 예시 마저 귀여운 charm, 한번 츄라이 해보세요!  
[charmbracelet/log: A minimal, colorful Go logging library 🪵 (](https://github.com/charmbracelet/log)[github.com](http://github.com)[)](https://github.com/charmbracelet/log)

---

### **안전하지 않은 문자열 처리**

go 1.20에 unsafe 패키지 내에 String과 StringData 함수가 추가되었습니다.  
각각 byte 포인터를 받아서 string을 만들거나, string 내의 byte 포인터를 반환합니다.  
주의해야할 것은 문자열은 기본적으로 불변이기 때문에 함부로 수정을 가하면 안됩니다.  
마찬가지로 같은 역할을 하는 Slice와 SliceData도 있으니 한번 확인해 보시기 바랍니다.  
[unsafe package - unsafe - Go Packages(String)](https://pkg.go.dev/unsafe#String)  
[unsafe package - unsafe - Go Packages(Slice)](https://pkg.go.dev/unsafe#Slice)

---

### **redis 공식 Go 클라이언트로의 승격**

레디스의 고 클라이언트 중 가장 인지도와 인기가 높은 go-redis가 레디스 공식 클라이언트로 내정되었습니다.  
go-redis가 공식 redis organization에 합류하게 되면서 더욱 발전된 클라이언트가 되기를 기대합니다.  
[Go-Redis Is Now an Official Redis Client | Redis](https://redis.com/blog/go-redis-official-redis-client/)  
[redis/go-redis: Type-safe Redis client for Golang (](https://github.com/redis/go-redis)[github.com](http://github.com)[)](https://github.com/redis/go-redis)

---

### **한번 쯤 어셈블리를 보고 싶지 않으신가요?**

lensm은 고 언어 어셈블리 뷰어로 여러분이 작성한 고 언어 프로그램의 코드의 어셈블리를 분석해서 보여줍니다.  
고 컴파일러에도 소스 코드 내의 어셈블리를 다룰 수 있는 부분이 있으니, 이참에 한번 공부해 볼까요?  
[loov/lensm: Go assembly and source viewer (](https://github.com/loov/lensm)[github.com](http://github.com)[)](https://github.com/loov/lensm)

---

### **Goland 부럽지 않은 vscode 만들기**

tooltitude는 기존에 고랜드가 제공하고 있던 코드 상의 편의 기능을 제공하는 익스텐션 입니다.  
레퍼런스 렌즈, 디프리케이티드 체크, 쉐도우된 심볼 감지, 에러 핸들링 코드 작성 등등의 편리한 기능을 제공합니다!  
[Tooltitude](https://www.tooltitude.com/)
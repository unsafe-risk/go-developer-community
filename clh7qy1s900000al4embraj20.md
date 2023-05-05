---
title: "23년 4월 첫번째 뉴스레터"
datePublished: Wed May 03 2023 13:41:07 GMT+0000 (Coordinated Universal Time)
cuid: clh7qy1s900000al4embraj20
slug: news-23-08
tags: newsletter

---

### **MCU에서 누가 더 빠른지 해볼까?**

마이크로컨트롤러인 ESP32에서 C, rust, MicroPython, 그리고 tiny-go의 성능을 비교한 아티클이 공개되었습니다.  
이 아티클에서는 4개의 언어를 다음 5개 부분의 실행 시간으로 측정 했습니다.

*1\. Fast Fourier Transform (FFT)*  
*2\. Cyclic Redundancy Check (CRC)*  
*3\. Secure Hash Algorithm (SHA)*  
*4\. Infinite Impulse Response (IIR)*  
*5\. Finite Impulse Response (FIR) filters*  
의외로 예상 외의 결과가 있으니 한번 확인해 보시기 바랍니다!

[Electronics | Free Full-Text | Performance Evaluation of C/C++, MicroPython, Rust and TinyGo Programming Languages on ESP32 Microcontroller (](https://www.mdpi.com/2079-9292/12/1/143)[mdpi.com](http://mdpi.com)[)](https://www.mdpi.com/2079-9292/12/1/143)

---

### **ChatGPT야, 나도 네 코인 좀 타볼래!**

제가 ChatGPT에게 좋은 개발자에 대해 물어보고, 들은 답변으로 블로깅을 하나 했습니다!  
답변이 하나하나 너무 좋아서, 공유하고 싶어 부끄럽지만 칸을 하나 할애했습니다.  
광고는 달려 있지 않으니 안심하고 챗지피티의 답변을 감상해주세요!  
그리고 해당 글의 제 감상은 별로 중요하지 않으니, 넘겨주세요.

[ChatGPT야, 좋은 개발자란 뭐라고 생각해? | snowmerak](https://snowmerak.pages.dev/posts/017_good_developer/)  

---

### **Our Mad Journey of Building a Vector Database in Go**

이 분야에 대해 잘 모르지만, Weaviate가 ML 모델을 위한 오픈소스 DB를 go로 만든 여정을 기록한 영상입니다.  
이 분들이 go로 오픈소스 DB를 만들면서 느낀 감상이나 겪은 경험들이 녹아 있으므로, 한번 들어보는 것도 좋다고 생각합니다.

[Our Mad Journey of Building a Vector Database in Go - Weaviate at FOSDEM 2023 - YouTube](https://www.youtube.com/watch?v=K1R7oK2piUM)

---

### **wasip1 플랫폼에 대한 지원 완료!**

고 언어가 벌써 wasi에 대한 지원을 시작했습니다!  
점점 더 커지는 웹어셈블리 기반 플랫폼에 고가 한자리 차지할 수 있길 바랍니다.

[cmd: add wasip1 support (479621) · Gerrit Code Review (](https://go-review.googlesource.com/c/go/+/479621)[googlesource.com](http://googlesource.com)[)](https://go-review.googlesource.com/c/go/+/479621)  
[all: add GOOS=wasip1 GOARCH=wasm port · Issue #58141 · golang/go (](https://github.com/golang/go/issues/58141)[github.com](http://github.com)[)](https://github.com/golang/go/issues/58141)  

---

### **Go에서 만나는 LLaMA**

LLaMA.go는 C++ 버전 LLaMA 코드를 기반으로 만들어진 프로젝트입니다.  
놀랍게도 pure go를 지향하고 있으며, 실제로도 그에 가깝게 작성되어 있습니다!

[gotzmann/llama.go: llama.go is like llama.cpp in pure Golang! (](https://github.com/gotzmann/llama.go)[github.com](http://github.com)[)](https://github.com/gotzmann/llama.go)  

---

### **Go는 역시 코드 생성을 해야지**

고 언어 생태계는 많은 경우 일반적인 케이스처럼 any나 제네릭을 사용하여 처리합니다.  
하지만 다양한 고성능이나 편의성을 위한 프로젝트일 경우엔 코드 생성을 해주기도 합니다.

마치 템플릿처럼요.

이번에 소개해드릴 GraphQL 라이브러리 또한 코드 생성 기반으로 이루어지는 라이브러리입니다!  
개인적인 감상은 공식 라이브러리보다 사용성은 훨 나은 느낌입니다.

[99designs/gqlgen: go generate based graphql server library (](https://github.com/99designs/gqlgen)[github.com](http://github.com)[)](https://github.com/99designs/gqlgen)

---

### **MongoDB 대체제를 노리는 귀여운 담비**

FerretDB가 얼마 전 1.0으로 버전을 올렸습니다.  
FerretDB는 postgres 위에서 동작하며, MongoDB를 대체할 목표를 가지고 있습니다.  
MongoDB와 동일한 쿼리 언어를 사용하여, 그를 분석 및 postgres에 사용하는 앱이 go로 작성되었습니다.

[FerretDB Blog | FerretDB Blog](https://blog.ferretdb.io/)

---

**goccy, 그는 신인가?**

goccy는 고 언어를 사용하는 개발자입니다.  
여러 쟁쟁한 프로젝트가 있지만, 우리에게 와닿을 수 있는 라이브러리를 두개 소개해드리겠습니다.

go-json와 go-yaml은 그가 만든 고성능 json, yaml 파서입니다.

그가 측정한 벤치마크에서 다른 관련 라이브러리를 압도했고, 어떻게 그런 성능을 낼 수 있었는지에 대한 아이디어를 서술해 놓았습니다.  
그 외에도 좋은 프로젝트가 많으니 구경해 보시면 좋을 거라 생각합니다.

[goccy/go-json: Fast JSON encoder/decoder compatible with encoding/json for Go (](https://github.com/goccy/go-json)[github.com](http://github.com)[)](https://github.com/goccy/go-json)  
[goccy/go-yaml: YAML support for the Go language (](https://github.com/goccy/go-yaml)[github.com](http://github.com)[)](https://github.com/goccy/go-yaml)
---
title: "[GDC] Weekly Newsletter August 5th"
datePublished: Sun Aug 25 2024 21:05:47 GMT+0000 (Coordinated Universal Time)
cuid: cm0a26rwk00020al65rdogcny
slug: gdc-weekly-newsletter-august-5th
tags: newsletter

---

## BleuIO와 Go를 사용하여 BLE 애플리케이션 구축하기

### Summary

이 글은 BleuIO USB 동글과 Go 프로그래밍 언어를 사용하여 Bluetooth 저에너지(BLE) 개발을 시작하는 방법을 단계별로 안내합니다. BleuIO는 사용하기 쉬운 AT 명령어로 BLE 애플리케이션 개발을 단순화하는 다재다능하고 사용자 친화적인 BLE USB 동글입니다. 

### Description

이 글은 개발 환경을 설정하고 BLE 동글과 상호 작용하는 간단한 Go 프로그램을 작성하고 BleuIO의 주요 기능을 살펴보는 방법을 보여줍니다.

### Discussion

1. **Go 언어의 장점:** Go는 간결하고 효율적인 코드 작성을 가능하게 하며, 시스템 프로그래밍 및 대규모 소프트웨어 개발에 적합한 선택입니다. Go의 강력한 동시성 지원, 빠른 컴파일 및 강력한 표준 라이브러리는 네트워크 프로그래밍, 클라우드 서비스, 그리고 BLE 애플리케이션에 인기 있는 언어로 만들었습니다.
2. **BleuIO의 장점:** BleuIO는 BLE 애플리케이션을 빠르고 쉽게 만들 수 있도록 돕는 BLE USB 동글입니다. 내장 AT 명령어를 사용하면 개발자는 복잡한 BLE 프로토콜이나 구성 없이 BLE 동글과 상호 작용할 수 있습니다. BleuIO는 다양한 운영 체제를 지원하여 모든 개발 환경에 유연한 도구입니다.
3. **BleuIO와 Go의 결합:** 이 글은 Go 언어를 사용하여 BleuIO USB 동글의 기능을 활용하는 방법을 보여줍니다. BleuIO의 AT 명령어와 Go 프로그래밍의 간편함을 결합하면 효율적이고 효과적인 BLE 애플리케이션을 구축할 수 있습니다.

### Features

- **AT 명령어:** BleuIO는 간편한 AT 명령어를 통해 BLE 동글을 제어할 수 있도록 합니다.
- **다양한 기능:** BleuIO는 장치 검색, 연결, 데이터 전송, 특성 읽기/쓰기 등 다양한 BLE 기능을 지원합니다.
- **Go 언어 호환성:** BleuIO는 Go 프로그래밍 언어와 완벽하게 호환되어 Go 개발자들이 쉽게 BLE 애플리케이션을 개발할 수 있도록 합니다.

### Usage

#### Installation

Go 프로젝트에서 BleuIO와 통신하기 위해서는 `go.bug.st/serial` 패키지를 설치해야 합니다.

```bash
go get go.bug.st/serial
```

#### BLE 장치 검색

다음 코드는 Go에서 BleuIO를 사용하여 BLE 장치를 검색하는 방법을 보여줍니다.

```go
package main

import (
	"fmt"
	"log"
	"time"

	"go.bug.st/serial"
)

func main() {
	// 시리얼 포트 열기
	mode := &serial.Mode{
		BaudRate: 9600,
	}
	port, err := serial.Open("/dev/cu.usbmodem4048FDE52CF21", mode) // 실제 시리얼 포트 경로로 변경
	if err != nil {
		log.Fatalf("시리얼 포트를 여는 데 실패했습니다: %v", err)
	}
	defer port.Close()

	// "AT+CENTRAL" 명령 보내기
	_, err = port.Write([]byte("AT+CENTRAL\r"))
	if err != nil {
		log.Fatalf("AT+CENTRAL 명령을 보내는 데 실패했습니다: %v", err)
	}
	fmt.Println("명령 전송: AT+CENTRAL")

	// 명령 처리를 위한 짧은 대기 시간
	time.Sleep(2 * time.Second)

	// "AT+CENTRAL" 명령에 대한 응답 읽기
	buf := make([]byte, 100)
	n, err := port.Read(buf)
	if err != nil {
		log.Fatalf("시리얼 포트에서 읽는 데 실패했습니다: %v", err)
	}
	fmt.Printf("AT+CENTRAL 명령에 대한 응답:\n%s\n", string(buf[:n]))

	// "AT+GAPSCAN=5" 명령 보내기 (5초 동안 스캔)
	_, err = port.Write([]byte("AT+GAPSCAN=5\r"))
	if err != nil {
		log.Fatalf("AT+GAPSCAN=5 명령을 보내는 데 실패했습니다: %v", err)
	}
	fmt.Println("명령 전송: AT+GAPSCAN=5")

	// 스캔 완료를 위한 대기 시간 (5초)
	time.Sleep(6 * time.Second)

	// "AT+GAPSCAN=5" 명령에 대한 응답 읽기
	buf = make([]byte, 1000)
	n, err = port.Read(buf)
	if err != nil {
		log.Fatalf("시리얼 포트에서 읽는 데 실패했습니다: %v", err)
	}

	// 응답 출력
	fmt.Printf("AT+GAPSCAN=5 명령에 대한 응답:\n%s\n", string(buf[:n]))
}
```

### Recommendation

BleuIO와 Go 언어를 사용하여 BLE 애플리케이션을 개발하는 것은 다양한 가능성을 제공합니다. 특히 간편한 인터페이스와 풍부한 기능을 통해 BLE 기반 애플리케이션 개발을 보다 쉽고 빠르게 진행할 수 있습니다.

### External Links

- **BleuIO 웹사이트:** [https://www.bleuio.com/](https://www.bleuio.com/)

### Caution

- **시리얼 포트 경로:** 코드에서 사용되는 시리얼 포트 경로 `/dev/cu.usbmodem4048FDE52CF21`은 시스템에 따라 다를 수 있습니다. 실제 시리얼 포트 경로를 확인해야 합니다.
- **AT 명령어:** BleuIO의 AT 명령어는 BLE 동글을 제어하는 데 사용됩니다. AT 명령어의 사용법과 의미를 이해하는 것이 중요합니다.

**참고:** 위 코드는 BLE 장치를 검색하는 기본적인 예시입니다. 실제 애플리케이션에서는 연결, 데이터 전송, 특성 읽기/쓰기 등 더욱 복잡한 기능을 구현해야 할 수 있습니다.
## Llama Nuts and Bolts: LLM의 내부 작동 방식 탐구

### 요약

"Llama Nuts and Bolts"는 Meta에서 개발한 대규모 언어 모델 Llama의 작동 방식을 실제 코드와 상세한 문서를 통해 탐구하는 GitHub 저장소입니다. 이 저장소는 Llama의 아키텍처, 학습 과정, 다양한 기능을 자세히 설명하여 LLM에 대한 깊이 있는 이해를 제공합니다.

### 설명

이 저장소는 Llama 모델의 구조, 학습 데이터셋, 학습 방법, 그리고 다양한 실험 결과를 제시합니다. 또한 텍스트 생성, 번역, 질문 답변, 요약, 코드 생성 등 Llama의 주요 기능을 예시와 함께 설명합니다. 특히, 이 프로젝트는 Python 생태계 외부에서 Llama 모델의 추론을 수행하는 데 중점을 두고 있으며, 외부 라이브러리 의존성을 최소화하여 LLM의 내부 작동 방식을 직접적으로 이해할 수 있도록 설계되었습니다.

### 토론

1. **LLM의 내부 작동 방식:** Llama의 아키텍처와 학습 과정을 분석하여 LLM의 작동 원리를 심층적으로 이해할 수 있습니다.
2. **LLM의 기능과 활용:** Llama의 다양한 기능을 실제 활용 사례를 통해 살펴보고 LLM의 잠재력을 확인할 수 있습니다.
3. **LLM의 한계와 윤리적 문제:** LLM의 한계와 윤리적 문제에 대한 논의를 통해 LLM 개발 및 사용에 대한 책임감을 강조합니다.

### 기능

- Llama 아키텍처와 구조에 대한 상세한 설명
- 학습 데이터셋 및 학습 방법에 대한 정보 제공
- 다양한 실험 결과 및 분석
- Llama의 기능 및 활용 예시 제공
- 외부 라이브러리 의존성 최소화
- Go 언어 기반 구현

### 사용

#### 설치

```bash
git clone https://github.com/adalkiran/llama-nuts-and-bolts.git
cd llama-nuts-and-bolts
```

#### Llama 모델 사용

본 저장소는 Llama 모델 자체를 제공하지 않습니다. Llama 모델을 사용하려면 Meta에서 공식적으로 제공하는 모델을 별도로 다운로드해야 합니다.

#### 예시 코드 활용

저장소 내 예시 코드를 활용하여 Llama의 기능을 직접 실행하고 결과를 확인할 수 있습니다.

### 추천

LLM의 내부 작동 방식에 대해 자세히 알고 싶거나, Llama 모델을 활용하여 개발을 진행하고자 하는 사람들에게 유용한 자료입니다. 특히, LLM의 이론적 개념을 넘어 실제 구현을 통해 LLM의 작동 원리를 탐구하고 싶은 사람들에게 추천합니다.

### 외부 링크

- [Meta Llama 공식 웹사이트](https://ai.facebook.com/blog/llama-large-language-model-meta-ai/)
- [Hugging Face Llama 모델 저장소](https://huggingface.co/models/facebook/llama-7b)

### 주의

- 본 저장소는 Llama 모델의 내부 작동 방식을 이해하는 데 도움을 주지만, 모델 자체를 제공하지 않습니다.
- Llama 모델 사용 시 Meta에서 제공하는 이용 약관 및 정책을 준수해야 합니다.
- LLM의 윤리적 문제 및 책임감 있는 사용에 대한 고려가 필요합니다.

## GoAstWriter: Go 코드 생성 도구

### 요약

GoAstWriter는 Go 언어로 작성된 코드 생성 도구입니다. Go의 AST(Abstract Syntax Tree)를 활용하여 Go 코드를 생성하고, 다양한 코드 생성 패턴을 제공합니다. Go 코드를 프로그램 방식으로 생성하고, 코드 생성 작업을 자동화하는 데 유용합니다.

### 설명

GoAstWriter는 Go의 `go/ast` 패키지를 활용하여 AST를 생성하고, 이를 사용하여 Go 코드를 생성하는 라이브러리입니다. 코드 생성 작업을 위한 다양한 기능을 제공하며, Go 언어의 문법을 준수하는 코드를 생성합니다.

### 기능

- Go 코드 생성
- 다양한 코드 생성 패턴 제공
- AST 조작 기능
- 코드 생성 작업 자동화

### 사용

#### 설치

```bash
go get github.com/palantir/goastwriter
```

#### 기본 사용

```go
package main

import (
	"fmt"
	"github.com/palantir/goastwriter"
	"github.com/palantir/goastwriter/astgen"
	"github.com/palantir/goastwriter/decl"
	"github.com/palantir/goastwriter/expression"
	"github.com/palantir/goastwriter/statement"
)

func main() {
	out, _ := goastwriter.Write("main",
		decl.NewImports(map[string]string{
			"fmt": "",
		}),
		&decl.Function{
			Name:     "main",
			FuncType: expression.FuncType{},
			Body: []astgen.ASTStmt{
				&statement.Expression{
					Expr: expression.NewCallFunction("fmt", "Println", expression.StringVal("Hello, World!")),
				},
			},
			Comment: "",
		},
	)

	fmt.Println(string(out))
}
```

```go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello, World!")
}
```

### 추천

- Go 코드 생성 작업을 자동화하고자 할 때
- 반복적인 코드 작성을 줄이고 싶을 때
- 복잡한 Go 코드를 프로그램 방식으로 생성해야 할 때

### 외부 링크

- [GoAstWriter GitHub 저장소](https://github.com/palantir/goastwriter)
- [Go 언어 공식 문서](https://go.dev/doc/)

### 주의

- GoAstWriter는 Go 언어의 AST를 활용하는 도구이므로, Go 언어의 문법과 AST 구조에 대한 이해가 필요합니다.
- 생성된 코드는 항상 검증해야 합니다.
- 코드 생성 과정에서 예상치 못한 오류가 발생할 수 있습니다.

## gonb: Jupyter를 위한 Go 노트북 커널

### Summary

gonb는 Jupyter 노트북을 위한 현대적인 Go 커널로, 개발자들이 Go 코드를 대화형으로 작성하고 실행할 수 있도록 지원합니다.  Go의 빠른 컴파일 속도를 활용하여 Go 코드를 컴파일하고 실행하며, 코드 완성, 컨텍스트 도움말, 오류 컨텍스트 등 다양한 기능을 제공합니다.

### Description

gonb는 Jupyter 환경에서 Go 코드를 사용하는 데 필요한 모든 기능을 제공합니다.  Go 언어의 기본적인 문법과 함수를 지원하며, Jupyter 노트북의 장점인 대화형 코딩, 결과 캐싱, 마크다운 지원 등을 통해 개발자들이 Go 코드를 효율적으로 작성하고 실행할 수 있도록 합니다.

### Discussion

1. **장점:** gonb는 Go 코드의 컴파일 속도를 활용하여 빠르게 실행됩니다. 또한, 코드 완성, 컨텍스트 도움말, 오류 컨텍스트 등의 기능을 통해 개발자들이 Go 코드를 쉽게 작성하고 이해할 수 있도록 지원합니다. 
2. **단점:** 아직 개발 초기 단계이기 때문에 모든 기능이 완벽하게 지원되지는 않습니다. 또한, 다른 Go 도구와의 통합 및 Windows 지원 등 일부 기능은 아직 개선이 필요합니다.
3. **개선 사항:** gonb는 더 많은 기능을 추가하고, 다른 Go 도구와의 통합을 강화해야 합니다.  Windows 지원을 추가하고, 커뮤니티 지원을 확대하여 사용자 접근성을 높일 필요가 있습니다.

### Features

- Go 코드의 빠른 컴파일 및 실행
- 코드 완성 및 컨텍스트 도움말 제공
- 오류 컨텍스트 제공
- 마크다운 및 HTML 지원
- 위젯 (슬라이더, 버튼) 지원
- Plotly 및 Apache ECharts 통합
- <code>go.mod</code> 및 <code>go.work</code> 지원
- <code>go test</code>를 통한 테스트 및 벤치마크 실행
- gdlv를 통한 디버깅
- <code>!</code>를 사용한 셸 명령어 실행
- GitHub Codespace, VS Code, Binder, Google Colab 등 다양한 환경에서 작동

### Usage

#### Installation

```bash
go install github.com/janpfeifer/gonb@latest
gonb --install
```

### Recommendation

gonb는 Go 개발자들이 Jupyter 노트북 환경에서 Go 코드를 효율적으로 사용하고 싶을 때 유용한 도구입니다.  Go의 빠른 컴파일 속도와 다양한 기능을 통해 개발자들이 Go 코드를 더 쉽고 빠르게 작성하고 실행할 수 있도록 지원합니다.

### External Links

- [GitHub Repository](https://github.com/janpfeifer/gonb)
- [GoDoc](https://pkg.go.dev/github.com/janpfeifer/gonb?tab=doc)
- [Docker Hub](https://hub.docker.com/r/janpfeifer/gonb_jupyterlab)
- [Google Colab](https://colab.research.google.com/drive/1vUd3SSoOm2K6UQLnkJQursZZx4CaIT_1?usp=sharing)

### Caution

- gonb는 아직 개발 초기 단계에 있으며, 모든 기능이 완벽하게 지원되지 않을 수 있습니다.
- gonb는 현재 Linux 및 macOS에서만 지원되며, Windows 지원은 아직 개발 중입니다.
- gonb를 사용하기 전에 최신 버전을 확인하고, 필요에 따라 업데이트를 수행하십시오. 

## FauxRPC: 가짜 RPC를 이용한 빠른 개발 및 테스트

### Summary

FauxRPC는 gRPC, gRPC-Web, Connect 및 REST 서비스에 대한 가짜 구현을 쉽게 생성하여 개발 및 테스트 속도를 높이는 강력한 도구입니다. Protobuf 기반 워크플로우를 사용하는 경우 이 도구가 도움이 될 수 있습니다.

### Description

FauxRPC는 실제 서비스의 동작을 모방하는 가짜 서비스를 생성하기 위해 Protobuf 정의를 활용합니다. 반환되는 가짜 데이터를 쉽게 구성하여 다양한 시나리오와 예외 사례를 시뮬레이션할 수 있습니다. *.proto 파일 또는 Protobuf 설명자 (binpb, json, txtpb, yaml 형식)를 입력으로 받아 gRPC/gRPC-Web/Connect 및 REST (google.api.http 주석이 정의된 경우)를 지원하는 서버를 자동으로 시작합니다. 설명자에는 *.proto 파일 집합에 있는 모든 정보가 포함됩니다. protoc 또는 buf build 명령을 사용하여 생성할 수 있습니다.

### Discussion

1. **빠른 개발 및 테스트**: 완전히 작동하는 백엔드 서비스에 의존하지 않고도 독립적으로 작업할 수 있습니다.
2. **격리 및 제어**: 제어된 가짜 데이터를 사용하여 격리된 환경에서 프론트엔드 구성 요소를 테스트할 수 있습니다.
3. **다중 프로토콜 지원**: gRPC, gRPC-Web, Connect 및 REST를 포함한 여러 프로토콜을 지원합니다.
4. **프로토타입 및 데모**: 전체 백엔드를 구축하지 않고도 빠르게 프로토타입과 데모를 만들 수 있습니다. "만들 때까지 가짜로 만들어라"는 원칙을 따릅니다.
5. **향상된 협업**: 프론트엔드와 백엔드 팀 간의 간극을 해소합니다.
6. **다른 도구와 잘 작동**: FauxRPC의 테스트 데이터는 정의된 protovalidate 제약 조건을 자동으로 따르려고 합니다.

### Features

- Protobuf 정의에서 가짜 gRPC, gRPC-Web, Connect 및 REST 서비스 생성
- 가짜 데이터 구성을 통한 다양한 시나리오 및 예외 사례 시뮬레이션
- 다중 프로토콜 지원
- protovalidate 제약 조건 지원

### Usage

#### Installation

```bash
go install github.com/sudorandom/fauxrpc/cmd/fauxrpc@latest
```

#### Descriptors 사용

example.proto 파일을 만들거나 기존 파일을 사용합니다:

```protobuf
syntax = "proto3";

package greet.v1;

message GreetRequest {
  string name = 1;
}

message GreetResponse {
  string greeting = 1;
}

service GreetService {
  rpc Greet(GreetRequest) returns (GreetResponse) {}
}
```

설명자 파일을 만들고 FauxRPC 서버를 시작하는 데 사용합니다:

```bash
$ buf build ./example.proto -o ./example.binpb
$ fauxrpc run --schema=./example.binpb
2024/08/17 08:01:19 INFO Listening on http://127.0.0.1:6660
2024/08/17 08:01:19 INFO See available methods: buf curl --http2-prior-knowledge http://127.0.0.1:6660 --list-methods
```

이제 gRPC, gRPC-Web 또는 Connect를 지원하는 도구를 사용하여 서비스를 호출할 수 있습니다. buf curl, grpcurl, Postman, Insomnia 모두 잘 작동합니다!

```bash
$ buf curl --http2-prior-knowledge http://127.0.0.1:6660/greet.v1.GreetService/Greet
{
  "greeting": "dream"
}
```

#### 서버 리플렉션

실행 중인 기존 gRPC 서비스를 에뮬레이트하려면 서버 리플렉션을 사용하여 FauxRPC 서비스를 시작할 수 있습니다:

```bash
$ fauxrpc run --schema=https://demo.connectrpc.com
```

#### BSR (Buf Schema Registry)에서

Buf에는 많은 스키마가 호스팅되는 스키마 레지스트리가 있습니다. 레지스트리의 이미지를 사용하여 FauxRPC를 사용하는 방법은 다음과 같습니다.

```bash
$ buf build buf.build/bufbuild/registry -o bufbuild.registry.json
$ fauxrpc run --schema=./bufbuild.registry.json
```

#### 여러 소스

`--schema` 옵션을 원하는 만큼 많이 정의할 수 있습니다. 즉, 여러 설명자에서 서비스를 추가하고 설명자와 서버 리플렉션을 혼합하여 사용할 수 있습니다.

```bash
$ fauxrpc run --schema=https://demo.connectrpc.com --schema=./example.binpb
```

### Recommendation

FauxRPC는 간단하고 효율적인 마이크로서비스 통신 솔루션을 찾는 개발자에게 추천합니다. 특히, 다양한 프로그래밍 언어를 사용하는 마이크로서비스 환경에서 유용하게 사용될 수 있습니다.

### External Links

- [FauxRPC GitHub Repository](https://github.com/sudorandom/fauxrpc)
- [FauxRPC Documentation](https://fauxrpc.com/docs/intro/)

### Caution

- FauxRPC는 실제 RPC 프로토콜을 사용하지 않으므로, 성능이 중요한 시스템에는 적합하지 않을 수 있습니다.
- 보안을 위해 HTTP 통신을 안전하게 구성해야 합니다.

## 고성능 및 안정적인 Golang 애플리케이션 구축을 넘어서: Zomato의 경험

### 요약

Zomato는 Golang을 사용하여 대규모 분산 시스템을 구축하는 동안 성능 및 안정성을 향상시키는 데 도움이 되는 다양한 방법과 도구를 사용했습니다. 이 글에서는 Zomato의 경험을 바탕으로 고성능 및 안정적인 Golang 애플리케이션을 구축하기 위한 다양한 팁과 전략을 소개합니다. 특히, Golang 1.19 버전 이후 도입된 GOMEMLIMIT 환경 변수를 활용하여 메모리 관리를 개선하고 OOM 문제를 해결한 Zomato의 사례를 자세히 살펴봅니다.

### 설명

Zomato는 Golang을 사용하여 수백만 명의 사용자에게 서비스를 제공하는 대규모 분산 시스템을 구축했습니다. Zomato의 엔지니어들은 Golang을 선택한 이유로 속도, 효율성 및 생산성을 들었습니다. 하지만 성장하는 시스템의 복잡성을 관리하고 성능 및 안정성을 유지하는 것은 어려운 과제였습니다. 이 글은 Zomato가 Golang 애플리케이션의 성능 및 안정성을 향상시키는 데 사용한 다양한 방법과 도구에 대한 통찰력을 제공합니다.

### 토론

1. **GOMEMLIMIT을 활용한 메모리 관리 개선:** 이전 버전의 Golang은 GOGC 환경 변수를 사용하여 가비지 컬렉션을 트리거했는데, 이는 라이브 힙 크기의 두 배에 도달할 때까지 실행되지 않아 OOM 문제를 일으킬 수 있었습니다. GOMEMLIMIT는 이러한 문제를 해결하기 위해 소프트 메모리 제한을 설정하여 가비지 컬렉터가 더 자주 실행되도록 합니다.
2. **Zomato/go/runtime 라이브러리 개발:** Zomato는 GOMEMLIMIT를 효과적으로 활용하기 위해 Zomato/go/runtime 라이브러리를 개발했습니다. 이 라이브러리는 런타임 중에 최적의 GOMEMLIMIT 값을 동적으로 계산하고, ECS 작업 및 컨테이너 제약 조건, 실시간 메모리 사용량 등을 고려합니다. 또한, GOMAXPROCS 환경 변수를 최적화하고 런타임 메트릭을 통합하여 모니터링을 강화합니다.
3. **실제 성과 및 개선:** Zomato는 250개 이상의 Golang 마이크로 서비스에 Zomato/go/runtime 라이브러리를 적용하여 GC CPU 사용량을 95% 이상 감소시키고 OOM 문제를 해결했습니다. 또한, CPU 사용량을 최대 50%까지 줄여 EC2 컴퓨팅 비용을 절감했습니다.

### 기능

- Zomato의 실제 경험을 바탕으로 Golang 애플리케이션의 성능 및 안정성 향상 전략 소개
- GOMEMLIMIT를 활용한 메모리 관리 개선 및 OOM 문제 해결 전략 상세 설명
- Zomato/go/runtime 라이브러리의 기능 및 사용법 설명
- 성능 및 안정성 개선을 위한 실질적인 팁과 권장 사항 제공

### 사용법

이 글은 Golang 애플리케이션 개발자를 위한 지침이므로 별도의 설치는 필요하지 않습니다. 

### 권장 사항

Golang 애플리케이션의 성능 및 안정성을 개선하기 위해 이 글에서 제시된 전략을 참고하고, 지속적인 모니터링과 개선을 통해 시스템을 최적화하는 것이 중요합니다. 특히 GOMEMLIMIT 환경 변수를 활용하여 메모리 관리를 개선하고, Zomato/go/runtime 라이브러리와 같은 도구를 활용하여 개발 프로세스를 간소화하는 것이 좋습니다.

### 외부 링크

- [Zomato 블로그](https://blog.zomato.com/)
- [Golang 공식 웹사이트](https://golang.org/)
- [GOMEMLIMIT 제안](https://go.googlesource.com/proposal/+/master/design/48409-soft-memory-limit.md)
- [runtime/debug.SetMemoryLimit](https://cs.opensource.google/go/go/+/go1.22.1:src/runtime/debug/garbage.go;l=236)
- [ECS task Metadata Endpoint](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-metadata-endpoint-v4.html)
- [Golang GC 가이드](https://tip.golang.org/doc/gc-guide#:~:text=This%20situation%2C%20where,the%20heap%20spike.)

### 주의

- GOMEMLIMIT는 메모리 누수를 해결할 수 없습니다. 메모리 누수는 가비지 컬렉터가 회수할 수 없는 메모리가 누적되는 현상으로, 라이브 힙 크기가 애플리케이션의 하드 메모리 제한을 초과하면 GOMEMLIMIT도 OOM 문제를 예방할 수 없습니다.
- Golang의 모든 기능을 완벽하게 이해하고 적용하는 데는 시간과 노력이 필요합니다.
- 성능 및 안정성을 개선하기 위한 최적의 방법은 프로젝트의 특성과 요구 사항에 따라 다를 수 있습니다.

## Tetrigo: Go로 작성된 테트리스 TUI 게임

### Summary

Tetrigo는 Go로 작성된 텍스트 기반 테트리스 게임입니다. 공식 2009 테트리스 디자인 가이드라인을 따르며, 사용자는 키보드로 블록을 움직이고 회전시켜 완벽한 줄을 만들고 점수를 얻을 수 있습니다. Tetrigo는 TUI, 게임 모드, 코어 테트리스 로직 등 세 가지 주요 구성 요소로 이루어져 있습니다.

### Description

Tetrigo는 터미널에서 실행되는 테트리스 게임을 제공하며, Bubble Tea 라이브러리를 사용하여 TUI를 구현했습니다. 이 프로젝트는 게임 개발에 관심 있는 개발자에게 Go를 활용하여 테트리스 게임을 구현하는 예시를 제공합니다.

### Discussion

1. **코드 구조:** Tetrigo는 잘 구성된 코드베이스를 가지고 있으며, 각 기능을 담당하는 패키지로 나뉘어져 있어 코드 이해도를 높입니다.
2. **확장성:** 게임 모드 패키지를 별도로 제공하여 다양한 게임 모드를 쉽게 추가할 수 있습니다. 또한, 코어 테트리스 로직 패키지는 사용자 정의 규칙과 요구 사항을 가진 게임 모드를 구현하는 데 유용합니다.
3. **학습 자료:** Tetrigo는 Go 프로그래밍 언어와 Bubble Tea 라이브러리를 배우는 데 좋은 예시입니다. 특히 TUI 개발에 관심 있는 개발자에게 도움이 될 수 있습니다.

### Features

- **키보드 제어:**  다양한 키를 사용하여 블록을 움직이고, 회전시키고, 홀드하고, 하드 드롭하고, 게임을 일시 정지하거나 종료할 수 있습니다.
- **게임 모드:**  Marathon, Sprint 등 다양한 게임 모드를 지원하며, 각 모드는 고유한 규칙과 요구 사항을 가지고 있습니다.
- **점수 시스템:** 완벽한 줄을 만들면 점수를 얻을 수 있으며, T-스핀 등 추가적인 점수 획득 방식이 구현될 예정입니다.
- **리더보드:** 게임 결과를 기록하고 다른 플레이어와 비교할 수 있습니다.

### Usage

#### Installation

Tetrigo는 깃허브 릴리즈 페이지에서 바이너리를 다운로드하거나 소스 코드에서 빌드하여 설치할 수 있습니다.

**바이너리 다운로드:**

1. [Tetrigo 릴리즈 페이지](https://github.com/Broderick-Westrope/tetrigo/releases)에서 운영 체제에 맞는 바이너리를 다운로드합니다.
2. 다운로드한 바이너리를 실행 파일이 있는 디렉토리로 이동합니다.
3. 터미널에서 `./tetrigo` (Linux/macOS) 또는 `tetrigo.exe` (Windows) 명령어를 실행합니다.

**소스 코드 빌드:**

1. Go 설치 및 설정을 확인합니다. `go.mod` 파일에는 최소 Go 버전이 명시되어 있습니다.
2. 터미널에서 `go install github.com/Broderick-Westrope/tetrigo/cmd/tetrigo@latest` 명령어를 실행하여 Tetrigo를 설치합니다.

#### 실행

터미널에서 `tetrigo` 명령어를 실행하면 Tetrigo가 시작됩니다.

**옵션:**

- `--config` 플래그를 사용하여 다른 TOML 구성 파일을 지정할 수 있습니다. 예: `tetrigo --config=/path/to/config.toml`
- `--db` 플래그를 사용하여 다른 SQLite 데이터베이스 파일을 지정할 수 있습니다. 예: `tetrigo --db=/path/to/data.db`
- `play` 서브 명령어를 사용하여 게임 모드를 직접 선택할 수 있습니다. 예: `tetrigo play marathon --level=5 --name=Brodie`

**도움말:**

- `tetrigo --help` 명령어를 실행하여 Tetrigo의 사용 방법 및 옵션을 확인할 수 있습니다.

### Recommendation

Go 프로그래밍 언어와 Bubble Tea 라이브러리를 배우려는 개발자 또는 텍스트 기반 게임 개발에 관심 있는 개발자에게 Tetrigo를 추천합니다.

### External Links

- [Tetrigo GitHub 저장소](https://github.com/Broderick-Westrope/tetrigo)
- [Bubble Tea 라이브러리](https://github.com/charmbracelet/bubbletea)

### Caution

- Tetrigo는 현재 개발 중이며, 일부 기능이 완벽하게 구현되지 않았을 수 있습니다.
- 게임 실행을 위해 Go와 Bubble Tea 라이브러리가 필요합니다.
- Tetrigo는 터미널에서 실행되는 게임으로, 그래픽 사용자 인터페이스(GUI)를 지원하지 않습니다.
- 게임 데이터는 SQLite 데이터베이스에 저장됩니다. 데이터베이스 파일은 게임 설정과 리더보드 정보를 포함합니다.

## ML-KEM Seeds: ML-KEM 키를 위한 시드 사용에 대한 합의

### Summary

NIST에서 발표한 최종 ML-KEM 사양(FIPS 203)은 개인 키를 시드(seed) 형태로 저장하는 것을 명시적으로 허용합니다. 이 글은 ML-KEM 키 저장 방식으로 시드를 사용하는 것을 표준화해야 한다고 주장합니다.

### Description

시드는 확장된 개인 키에 비해 여러 가지 장점을 제공합니다. 가장 큰 장점은 크기입니다. 시드는 64바이트인 반면 확장된 개인 키는 ML-KEM 매개변수 집합에 따라 1 632, 2 400 또는 3 168 바이트입니다. 

또한, 시드는 항상 유효한 반면, 확장된 개인 키는 유효성 검사가 필요합니다. FIPS 203에서는 확장된 개인 키의 두 부분(암호화 키의 사전 계산된 해시 및 암호화 키 자체)의 일관성을 확인하기 위해 추가적인 검사를 수행해야 합니다. 

### Discussion

1. **시드는 유효성 검사가 필요하지 않아 더 간단하고 안전합니다.** 
2. **시드는 확장된 개인 키보다 크기가 작아 저장 및 전송에 효율적입니다.**
3. **시드는 확장된 개인 키보다 더 나은 메모리 내 형식을 제공합니다.**

### Features

- 시드는 64바이트로 크기가 작습니다.
- 시드는 항상 유효합니다.
- 시드는 메모리 내 형식으로도 적합합니다.

### Recommendation

ML-KEM 구현에서 시드를 사용하는 것이 좋습니다. 시드는 더 간단하고 안전하며 효율적입니다.

### External Links

- [ML-K-EM Seeds GitHub 저장소](https://github.com/filippo-io/ml-k-em-seeds)
- [ML-K-EM Seeds 문서](https://words.filippo.io/dispatches/ml-kem-seeds/)

### Caution

- 시드는 보안이 매우 중요합니다. 시드를 안전하게 보관해야 합니다.
- 시드를 사용하는 ML-KEM 구현은 최신 버전의 FIPS 203 사양을 준수해야 합니다.

## Hugot: Golang용 Huggingface 변환기 파이프라인

### Summary

Hugot는 Golang 애플리케이션에서 Huggingface 변환기 파이프라인을 쉽고 확장 가능하며 번거롭지 않게 실행하도록 설계된 Golang 라이브러리입니다. 이 라이브러리는 다음과 같은 원칙을 기반으로 구축되었습니다.

- 원본 Huggingface Python 구현과의 충실도: 구현된 파이프라인에 대한 Huggingface 추론 구현을 정확하게 복제하여 Python에서 훈련 및 테스트된 모델을 Golang 애플리케이션에 원활하게 배포할 수 있도록 하는 것이 목표입니다.
- 번거롭지 않고 성능이 뛰어난 프로덕션 사용: Huggingface 모델의 ONNX 내보내기를 독점적으로 지원합니다. ONNX 버전이 없는 Pytorch 변환기 모델은 <a href="https://huggingface.co/docs/optimum/index" rel="nofollow">Huggingface Optimum</a>을 통해 ONNX로 쉽게 내보낼 수 있으며, 이 라이브러리에서 사용할 수 있습니다.
- 하드웨어에서 실행: 이 라이브러리는 REST API를 사용해야 하는 성능 저하 없이 또는 Golang과 통신하는 Python RPC 서비스를 설정하고 유지 관리하는 번거로움 없이, Golang 애플리케이션과 긴밀하게 결합된 변환기 모델을 실행하려는 사용자를 위해 설계되었습니다.

### Description

Hugot는 데이터 과학자, 데이터 분석가, 개발자를 위해 설계된 Golang 라이브러리입니다. Hugot는 데이터 처리, 변환, 시각화, 모델링, 예측과 같은 다양한 데이터 분석 작업에 필요한 종합적인 기능을 제공합니다. 이 라이브러리는 Pandas, NumPy, Matplotlib, Scikit-learn과 같은 인기 있는 Python 라이브러리를 기반으로 하므로 사용자는 기존 코드를 쉽게 통합하고 사용할 수 있습니다.

### Discussion

1. **데이터 처리 및 변환:** Hugot는 데이터 정제, 결합, 변환, 필터링과 같은 데이터 처리 및 변환 작업에 필요한 광범위한 기능을 제공합니다. 간결한 코드를 사용하여 복잡한 데이터 조작 작업을 수행할 수 있습니다.
2. **데이터 시각화:** Hugot는 데이터 시각화를 위한 다양한 도구를 제공합니다. 히스토그램, 산점도, 박스 플롯 등을 포함한 다양한 차트와 플롯을 생성하여 데이터를 탐색하고 패턴을 파악할 수 있습니다.
3. **머신러닝 모델링:** Hugot는 선형 회귀, 로지스틱 회귀, 의사 결정 트리, 서포트 벡터 머신 등과 같은 다양한 머신러닝 알고리즘을 제공합니다. Hugot의 간편한 API를 사용하여 모델을 훈련하고 평가할 수 있습니다.

### Features

- 사용자 친화적인 인터페이스
- 강력한 데이터 처리 및 변환 기능
- 데이터 시각화 도구
- 다양한 머신러닝 모델
- Pandas, NumPy, Matplotlib, Scikit-learn과의 통합

### Recommendation

Hugot는 다양한 데이터 분석 작업을 간소화하기 위한 강력하고 유연한 도구입니다. 특히 데이터 과학자, 데이터 분석가, 개발자에게 유용합니다.

### External Links

- Hugot GitHub 저장소: [https://github.com/knights-analytics/hugot](https://github.com/knights-analytics/hugot)

### Caution

- Hugot는 아직 개발 초기 단계에 있으며, 기능이 지속적으로 업데이트되고 있습니다.

## Go 기반 머신러닝 프레임워크: Gomlx

### Summary

Gomlx는 Go 프로그래밍 언어를 위한 빠르고 사용하기 쉬운 머신러닝 및 일반적인 수학 라이브러리 및 도구 집합입니다. Go에서 PyTorch, Jax, TensorFlow와 유사한 역할을 수행하며, JIT 컴파일을 통해 CPU와 GPU (곧 TPU도 지원 예정)를 사용합니다. OpenXLA/PJRT 기반으로 구축되어 LLVM을 사용하여 코드를 JIT 컴파일합니다. Google의 Jax와 TensorFlow와 동일한 엔진을 사용하며, 많은 경우 동일한 속도를 제공합니다.

### Description

Gomlx는 Go 언어를 위한 머신러닝 개발 환경을 제공하며, 다양한 머신러닝 알고리즘, 자동 미분, 레이어 라이브러리, 훈련 라이브러리, 최적화기, 손실 및 지표 등을 포함하고 있습니다. Gomlx의 목표는 Go 언어로 머신러닝 모델을 개발하고 배포하는 것을 간단하고 효율적으로 만드는 것입니다.

### Features

- **다양한 머신러닝 알고리즘:** 선형 회귀, 로지스틱 회귀, 딥 뉴럴 네트워크 등
- **자동 미분:** 역전파를 위한 그래디언트 계산
- **레이어 라이브러리:** FFN 레이어, 활성화 함수, 배치 정규화, 합성곱, 풀링, 드롭아웃, 멀티 헤드 어텐션 등
- **훈련 라이브러리:** 모델 훈련 및 평가, Jupyter 노트북에서의 시각화 기능
- **최적화기:** SGD, Adam, AdamW, Adamax 등
- **손실 및 지표:** 다양한 손실 함수 및 성능 측정 지표
- **GPU 지원:** OpenXLA/PJRT를 통해 GPU 가속 지원
- **Jupyter 노트북 통합:** GoNB (Go 커널)을 사용하여 Jupyter 노트북에서 Gomlx 사용 가능
- **Docker 이미지:** JupyterLab 및 GoNB와 통합된 Docker 이미지 제공

### Usage

#### 설치

Gomlx는 Docker 이미지 또는 직접 설치를 통해 사용할 수 있습니다.

**Docker 이미지 사용:**

1. Docker 이미지를 다운로드합니다: `docker pull janpfeifer/gomlx_jupyterlab:latest`
2. Docker 컨테이너를 실행합니다: `docker run -it --rm -p 8888:8888 -v "${PWD}":/home/jupyter/work janpfeifer/gomlx_jupyterlab:latest`
3. 터미널에 표시된 URL을 브라우저에서 열면 JupyterLab이 실행됩니다.

**직접 설치:**

1. `gopjrt` 설치: [설치 지침](https://github.com/gomlx/gopjrt?#installing)을 참조하세요.
2. Nvidia CUDA 지원 (선택 사항): 필요한 경우 [설치 지침](https://github.com/gomlx/gopjrt?#installing)을 참조하세요.
3. `hdf5-tools` 설치: `sudo apt install hdf5-tools` (Linux)
4. Gomlx 라이브러리를 설치합니다: `go get github.com/gomlx/gomlx`

### Recommendation

Go 언어를 사용하여 머신러닝 모델을 개발하려는 개발자에게 Gomlx를 추천합니다. 특히, OpenXLA/PJRT를 통한 GPU 지원, Jupyter 노트북 통합, Docker 이미지 제공 등의 기능은 머신러닝 개발을 더욱 효율적으로 만들어줍니다.

### External Links

- [Gomlx GitHub 저장소](https://github.com/gomlx/gomlx)
- [Gomlx 문서](https://gomlx.dev/)

### Caution

- Gomlx는 아직 개발 중인 라이브러리이므로, 일부 기능이 완벽하게 구현되지 않았을 수 있습니다.
- Gomlx는 Go 언어를 사용해야 하므로, Go 언어에 대한 기본적인 지식이 필요합니다.
- Gomlx는 OpenXLA/PJRT에 의존합니다. 따라서 OpenXLA/PJRT를 설치하고 구성하는 방법을 알아야 합니다.

## SKS: 랩탑의 보안 하드웨어를 추상화하는 Go 라이브러리

### 요약

SKS는 Facebook에서 개발한 Go 라이브러리로, 랩탑에 탑재된 TPM(Trusted Platform Module)이나 Secure Enclave와 같은 하드웨어 보안 모듈을 추상화하여 사용자들이 단일 API를 통해 이러한 기능을 활용할 수 있도록 합니다. 

### 설명

현대 랩탑 대부분은 TPM 또는 Secure Enclave와 같은 하드웨어 보안 모듈을 탑재하고 있습니다. 이러한 모듈은 키 생성, 서명, 암호화와 같은 공통 기능을 제공하지만, 작동 방식과 API 구현이 상당히 다릅니다. SKS는 이러한 차이점을 추상화하여 사용자들이 이러한 하드웨어 보안 기능을 일관되게 사용할 수 있도록 돕습니다.

### 토론

1. **SKS의 장점:** SKS를 사용하면 다양한 하드웨어 보안 모듈에 대한 코드를 일관되게 작성할 수 있어 개발 시간을 단축하고 유지 관리를 간소화할 수 있습니다.
2. **SKS의 단점:** 현재로서는 SKS가 모든 하드웨어 보안 모듈을 지원하는 것은 아니며, 특정 기능은 플랫폼에 따라 지원되지 않을 수 있습니다.
3. **SKS의 미래:** SKS는 앞으로 더 많은 하드웨어 보안 모듈을 지원하고 더 많은 기능을 구현할 예정입니다.

### 기능

- TPM 2.0과 Secure Enclave(T1 및 T2 칩셋) 지원
- ECDSA P256 키 생성
- 하드웨어 내에서 키 검색
- 임의 데이터 서명
- 하드웨어에서 키 제거

### 사용법

#### 설치

```bash
go get github.com/facebookincubator/sks
```

#### 키 생성 및 사용 예시

```go
import (
	"crypto/rand"
	"fmt"
	"github.com/facebookincubator/sks"
)

func main() {
	// label:tag로 식별되는 키를 가져옵니다.
	key := sks.FromLabelTag("label:tag")

	// 새로운 키를 생성합니다.
	signer, err := sks.NewKey(key.Label(), key.Tag(), false, true)
	if err != nil {
		fmt.Println("Error creating key:", err)
		return
	}

	// 임의 데이터를 생성합니다.
	digest := make([]byte, 32)
	rand.Read(digest)

	// 데이터를 서명합니다.
	signature, err := signer.Sign(nil, digest, nil)
	if err != nil {
		fmt.Println("Error signing data:", err)
		return
	}

	// 키를 제거합니다.
	err = signer.Remove()
	if err != nil {
		fmt.Println("Error removing key:", err)
		return
	}

	fmt.Println("Key successfully created, signed data, and removed.")
}
```

### 추천

랩탑에서 하드웨어 보안 모듈을 활용하여 키 생성, 서명, 암호화 기능을 사용하고자 하는 Go 개발자들에게 SKS를 추천합니다.

### 외부 링크

- [SKS GitHub 저장소](https://github.com/facebookincubator/sks)

### 주의

- SKS는 현재 베타 버전이며, API가 변경될 수 있습니다.
- 특정 기능은 플랫폼에 따라 지원되지 않을 수 있습니다.
- SKS를 사용하기 전에 지원되는 하드웨어 및 플랫폼 목록을 확인해야 합니다.

## 커널 네트워킹에서 TLS 오프로드 이해하기

### 요약

이 문서는 리눅스 커널 네트워킹 스택에서 TLS 오프로드의 개념, 구현 및 활용에 대해 설명합니다. TLS 오프로드는 네트워크 인터페이스 카드(NIC) 또는 다른 하드웨어 가속기가 TLS 암호화 및 복호화 작업을 처리하도록 하는 기술로, 서버의 CPU 부담을 줄이고 성능을 향상시킵니다.

### 설명

TLS 오프로드는 웹 서버와 같은 애플리케이션에서 TLS 암호화/복호화 작업을 NIC 또는 하드웨어 가속기에 위임하여 CPU 사용량을 줄이고 네트워크 처리량을 향상시키는 기술입니다. 이는 특히 많은 수의 동시 연결을 처리해야 하는 서버에서 유용합니다.

### 논의

1. **TLS 오프로드의 작동 방식**: 커널은 TLS 연결을 설정한 후, 사용자 공간에서 TLS 상위 계층 프로토콜(ULP)을 활성화하고 암호화 연결 상태를 설치할 수 있습니다. 커널은 장치 구성 및 오프로드 옵션에 따라 소프트웨어 암호화 모드, 패킷 기반 NIC 오프로드 모드, 전체 TCP NIC 오프로드 모드 등 세 가지 모드로 작동합니다.
2. **TLS 오프로드 장치 구성**: 장치 드라이버는 초기화 중에 <code class="docutils literal notranslate"><span class="pre">NETIF_F_HW_TLS_RX</span></code> 및 <code class="docutils literal notranslate"><span class="pre">NETIF_F_HW_TLS_TX</span></code> 기능을 설정하고 <code class="docutils literal notranslate"><span class="pre">struct</span> <span class="pre">tlsdev_ops</span></code> 포인터를 장치의 <code class="docutils literal notranslate"><span class="pre">tlsdev_ops</span></code> 멤버에 설치합니다. 커널은 TLS 암호화 연결 상태를 설치할 때 장치가 오프로드 기능을 지원하는지 확인하고 오프로드를 시도합니다. 오프로드가 실패하면 연결은 소프트웨어 방식으로 처리됩니다.
3. **오프로드 동작**: 장치는 연결 상태를 유지하고 패킷을 처리하며, 오류 발생 시 패킷을 소프트웨어 폴백으로 전달합니다. 또한, 장치는 오프로드 통계를 보고하고, 리싱크 처리를 통해 오류를 처리합니다.

### 기능

- **CPU 부담 감소**: TLS 암호화/복호화 작업을 NIC에 위임하여 CPU 사용량을 줄입니다.
- **성능 향상**: 하드웨어 가속을 통해 네트워크 처리량을 향상시킵니다.
- **낮은 지연 시간**: 빠른 암호화/복호화 처리로 인해 응답 시간이 단축됩니다.

### 사용법

#### 설치

TLS 오프로드 기능을 사용하려면 지원되는 NIC 또는 하드웨어 가속기가 필요하며, 해당 드라이버가 커널에 설치되어야 합니다.

#### TLS 오프로드 활성화

TLS 오프로드 기능을 활성화하기 위해 커널 파라미터 또는 NIC 드라이버 옵션을 구성해야 합니다. 구체적인 방법은 사용하는 NIC 또는 하드웨어 가속기에 따라 다릅니다.

#### TLS 오프로드 설정

TLS 오프로드를 사용할 때는 암호화/복호화 알고리즘, 키 교환 방법, 인증 방법 등을 설정해야 합니다. 이러한 설정은 사용하는 웹 서버 소프트웨어 또는 TLS 라이브러리에서 관리합니다.

### 권장 사항

- TLS 오프로드 기능을 사용하기 전에 하드웨어 요구 사항을 확인하고 지원되는 NIC 또는 하드웨어 가속기를 사용하는지 확인하십시오.
- TLS 오프로드를 구성하기 전에 해당 NIC 또는 하드웨어 가속기의 문서를 참조하십시오.
- 보안 문제를 방지하기 위해 TLS 오프로드를 사용할 때 신뢰할 수 있는 암호화/복호화 알고리즘을 선택하고 강력한 보안 설정을 적용하십시오.

### 외부 링크

- [Linux 커널 문서: TLS 오프로드](https://docs.kernel.org/networking/tls-offload.html)
- [OpenSSL: TLS 오프로드](https://www.openssl.org/docs/man1.1.1/man1/openssl-s_client.html)

### 주의 사항

- TLS 오프로드는 모든 NIC 또는 하드웨어 가속기에서 지원되지 않을 수 있습니다.
- TLS 오프로드는 추가 구성 및 보안 문제를 야기할 수 있으므로 주의해야 합니다.
- TLS 오프로드 기능을 사용할 때는 보안 문제를 방지하기 위해 신중하게 설정하고 관리해야 합니다.

## Permify: Google Zanzibar에서 영감을 받은 오픈소스 권한 관리 서비스

### Summary

Permify는 Google Zanzibar에서 영감을 받아 설계된 오픈소스 권한 관리 서비스입니다. Permify는 모든 애플리케이션에 대한 세분화되고 확장 가능한 권한 관리 시스템을 구축하고 관리하기 위해 설계되었습니다. Permify를 사용하면 몇 분에서 며칠 만에 권한 관리를 구현하고 관리할 수 있어 수개월 동안 인프라 구축에 시간을 낭비할 필요가 없습니다.

### Description

Permify는 개발자가 애플리케이션에 대한 액세스 제어를 구현하고 관리하는 데 도움이 되는 오픈소스 프레임워크입니다. Permify는 정책 기반 액세스 제어(PBAC) 모델을 따르며, 개발자가 액세스 제어 정책을 쉽게 정의하고 관리할 수 있도록 지원합니다. 또한 Permify는 다양한 데이터베이스와 통합되어 사용자, 그룹, 리소스 및 권한에 대한 정보를 효율적으로 관리할 수 있습니다.

### Features

- **세분화된 권한 관리:** 리소스별, 계층적, 컨텍스트 인식 권한과 정책을 생성할 수 있습니다. 
- **확장성:** Google Zanzibar에서 영감을 받은 검증된 인프라로 10ms 이내의 빠른 액세스 확인 응답 시간을 제공합니다.
- **중앙 집중식 권한 관리:** 코드베이스와 애플리케이션 로직에서 권한 로직을 분리하여 권한을 쉽게 추론하고 테스트 및 디버깅할 수 있습니다.
- **테넌트별 권한 관리:** 벤더/조직(테넌트)에 대해 격리된 권한 로직과 사용자 지정 권한을 설정하고 한 곳에서 관리할 수 있습니다.

### Recommendation

Permify는 액세스 제어를 필요로 하는 다양한 애플리케이션에 적합한 프레임워크입니다. Permify는 사용하기 쉽고 확장 가능하며 다양한 기능을 제공합니다.

### External Links

- [Permify 공식 웹사이트](https://permify.co/)
- [Permify GitHub 저장소](https://github.com/Permify/permify)
- [Permify 문서](https://docs.permify.co/)
- [Permify 플레이그라운드](https://play.permify.co/)
- [Permify Discord 채널](https://discord.gg/n6KfzYxhPp)

### Caution

- Permify는 아직 개발 단계에 있으며 변경될 수 있습니다.
- Permify는 다양한 데이터베이스를 지원하지만 일부 데이터베이스에서는 추가 설정이 필요할 수 있습니다.

## Golang 보안 검토 가이드

### 요약

이 글은 Golang 애플리케이션의 보안 취약점을 발견하고 수정하는 데 도움이 되는 실용적인 가이드입니다. Golang 개발자가 공통적인 보안 취약점을 이해하고 이를 방지하기 위한 최상의 방법을 배우는 데 도움이 되는 단계별 지침과 실제 예제를 제공합니다. 이 글에서는 흔히 발생하는 보안 취약점과 그 해결 방법을 다루며, 실제 코드 예제와 함께 상세히 설명합니다.

### 설명

Golang 애플리케이션의 보안은 매우 중요하며, 이 가이드는 개발자가 보안 문제를 해결하는 데 도움이 되는 다양한 전략과 권장 사항을 제공합니다. 이 가이드에서는 SQL 주입, XSS, CSRF, 인증 및 권한 부여, 암호화, 로깅, 에러 처리, 의존성 관리 등과 같은 다양한 보안 문제를 다룹니다. 각 문제에 대한 심층적인 분석과 함께, 실제 코드 예제를 통해 해결 방법을 보여줍니다. 또한, ReDoS, 잘못된 정규 표현식 사용, 파일 포함, XXE, 암호화, 세션 제어, 액세스 제어, 에러 처리, 로깅, CSRF 등 다양한 보안 취약점을 다루고 있습니다.

### 토론

1. **Golang 애플리케이션의 일반적인 보안 취약점**
   -  RCE(Remote Code Execution)
   -  SQL Injection
   -  XSS(Cross-Site Scripting)
   -  SSRF(Server-Side Request Forgery)
   -  File Inclusion
   -  XXE(XML External Entity)
   -  Authentication
   -  Access Control
   -  Cryptography
   -  Error Handling and Logging
   -  CSRF(Cross-Site Request Forgery)
   -  Regular Expressions
2. **각 취약점을 해결하기 위한 최상의 방법**
   -  각 취약점에 대한 구체적인 예제와 함께 해결 방안 제시
   -  보안 코딩 가이드라인과 권장 사항 제공
3. **보안 테스트 도구와 기술**
   -  Snyk, ReDoS Checker 등 다양한 보안 테스트 도구 활용 방법 소개
   -  취약점 분석 및 해결을 위한 기술 및 전략 제시

### 기능

- Golang 애플리케이션의 일반적인 보안 취약점 목록
- 각 취약점을 해결하기 위한 단계별 지침
- 보안 테스트 도구와 기술 목록
- 실제 예제와 코드 스니펫
- 다양한 보안 관련 자료 및 외부 링크 제공

### 사용법

#### 보안 취약점 검사

1. 이 가이드에 나와 있는 지침에 따라 Golang 애플리케이션을 검사합니다.
2. 각 취약점 항목별 코드 예제를 참고하여 애플리케이션 코드를 분석합니다.
3. Snyk, ReDoS Checker 등 보안 테스트 도구를 활용하여 취약점을 식별합니다.

#### 취약점 수정

1. 식별된 취약점을 해결하기 위해 제공된 권장 사항을 따릅니다.
2.  보안 관련 코드 수정 및 개선을 진행합니다.

### 권장 사항

Golang 개발자는 이 가이드를 참고하여 애플리케이션의 보안을 강화하는 데 필요한 지식을 습득해야 합니다.  특히,  RCE, SQL 주입, XSS, CSRF 등과 같은 흔한 취약점에 대한 이해를 높이고, 안전한 코드 작성 습관을 갖도록 노력해야 합니다.

### 외부 링크

- [Golang 보안 문서](https://golang.org/doc/security)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Snyk](https://snyk.io/)
- [ReDoS Checker](https://devina.io/redos-checker)
- [MarsCode](https://www.marscode.com/)
- [MarsCode Discord](https://discord.gg/marscode)

### 주의 사항

- 이 가이드는 Golang 보안의 모든 측면을 다루는 것은 아닙니다.
- 이 가이드는 지속적인 보안 노력의 일부로 간주되어야 합니다.
- 보안 위협은 항상 진화하고 있으므로 최신 보안 권장 사항과 패치를 최신 상태로 유지하십시오. 
-  자체 암호화 로직 구현은 위험하며, 검증된 라이브러리 사용을 권장합니다.

## Chisel: HTTP를 통한 빠른 TCP/UDP 터널

### Summary

Chisel은 HTTP를 통해 전송되는 빠른 TCP/UDP 터널로, SSH를 통해 보안을 강화합니다. 클라이언트와 서버 모두를 포함하는 단일 실행 파일로 Go(golang)로 작성되었습니다. Chisel은 주로 방화벽을 통과하는 데 유용하지만 네트워크에 대한 안전한 엔드포인트를 제공하는 데에도 사용할 수 있습니다.

### Description

Chisel은 네트워크 트래픽을 HTTP를 통해 안전하게 전달하는 터널링 도구입니다. SSH 프로토콜을 사용하여 보안을 강화하며, 클라이언트와 서버를 모두 포함하는 단일 실행 파일로 제공됩니다. 이를 통해 방화벽을 우회하거나 네트워크에 안전한 접근 권한을 제공할 수 있습니다.

### Discussion

1. **Chisel은 어떤 상황에 유용한가요?**
    - 방화벽을 우회해야 할 때
    - 네트워크 내부의 서비스에 안전하게 액세스해야 할 때
    - 원격 서버에 대한 SSH 연결을 설정해야 할 때
    - SOCKS 프록시를 통해 연결을 설정해야 할 때

2. **Chisel의 장점은 무엇인가요?**
    - 빠르고 효율적인 터널링
    - SSH를 통한 안전한 연결
    - 단일 실행 파일로 간편한 사용
    - 다양한 플랫폼 지원
    - 다양한 기능 제공 (SOCKS5 프록시, 역방향 포트 포워딩 등)

3. **Chisel의 단점은 무엇인가요?**
    - 복잡한 설정이 필요할 수 있음
    - 일부 PaaS 환경에서 WebSockets 지원이 제한적일 수 있음

### Features

- HTTP를 통한 빠른 TCP/UDP 터널링
- SSH를 통한 안전한 연결
- 클라이언트 및 서버를 포함하는 단일 실행 파일
- 사용자 인증 및 핑거프린트 매칭을 통한 보안 강화
- 지수형 백오프를 통한 클라이언트 자동 재연결
- 다중 터널 엔드포인트 지원
- SOCKS5 프록시 및 HTTP CONNECT 프록시 지원
- 역방향 포트 포워딩 지원
- 서버에서 역방향 프록시 역할 수행
- 서버에서 SOCKS5 연결 허용
- 클라이언트에서 역방향 포트 포워딩을 통한 SOCKS5 연결 허용
- stdio를 통한 클라이언트 연결 지원 (SSH -o ProxyCommand 기능)

### Usage

#### 설치

```bash
$ go install github.com/jpillora/chisel@latest
```

#### 서버 실행

```bash
$ chisel server --keyfile <ck-base64 문자열 또는 파일 경로> -p 9312 --socks5
```

#### 클라이언트 실행

```bash
$ chisel client --fingerprint <서버 출력 확인> <서버 주소>:9312 socks
```

### Recommendation

Chisel은 네트워크에 대한 안전하고 효율적인 터널링 기능이 필요한 개발자 또는 시스템 관리자에게 추천합니다. 특히 방화벽을 우회하거나 원격 서버에 대한 안전한 접근 권한을 제공하는 데 유용합니다.

### External Links

- [Chisel 공식 문서](https://godoc.org/github.com/jpillora/chisel)
- [Chisel GitHub 저장소](https://github.com/jpillora/chisel)

### Caution

- Chisel은 Go 언어로 작성되었으므로 Go 언어에 대한 기본적인 이해가 필요합니다.
- Chisel은 다양한 설정 옵션을 제공하므로 사용 환경에 맞는 적절한 설정을 적용해야 합니다.
- 일부 PaaS 환경에서는 WebSockets 지원이 제한적일 수 있으므로 사용 전에 지원 여부를 확인해야 합니다.

## Anthropic의 교육 과정

### Summary

Anthropic의 `courses` 저장소는 Anthropic에서 개발한 Claude 모델을 사용하는 방법을 배우는 데 도움이 되는 다양한 교육 자료를 제공합니다. 이 저장소는 Claude SDK를 사용하는 방법, 프롬프트 엔지니어링 기법 및 Claude를 사용한 도구 구현에 대한 과정을 포함하고 있습니다.

### Description

`courses` 저장소는 Anthropic에서 개발한 Claude AI 모델과 관련된 교육 자료를 제공합니다. 이 저장소는 Jupyter Notebook 파일, 예제 코드, 설명 문서 등으로 구성되어 있습니다. 이를 통해 사용자는 Claude 모델의 다양한 기능을 배우고 실제 애플리케이션에 적용하는 방법을 익힐 수 있습니다. 

### Discussion

1. **Claude SDK 사용법:** 이 저장소에는 Claude SDK를 사용하여 API 키를 얻고, 모델 매개변수를 조정하고, 멀티모달 프롬프트를 작성하고, 응답을 스트리밍하는 등 Claude 모델과 상호 작용하는 방법을 배우는 데 도움이 되는 과정이 포함되어 있습니다.
2. **프롬프트 엔지니어링 기법:** Claude 모델을 효과적으로 활용하려면 적절한 프롬프트를 작성하는 것이 중요합니다. 이 저장소는 프롬프트 엔지니어링과 관련된 다양한 기법을 다루는 과정을 제공합니다.
3. **도구 구현:** Claude 모델을 활용하여 복잡한 작업을 수행하려면 도구를 사용하는 것이 필요합니다. 이 저장소는 Claude에서 도구를 구현하고 사용하는 방법을 배우는 데 도움이 되는 과정을 제공합니다.

### Features

- **Jupyter Notebook 기반 과정:** Jupyter Notebook 파일을 통해 이론 학습과 실제 코드 작성을 병행할 수 있어 학습 효과를 높입니다.
- **다양한 예제 코드:** 다양한 Claude 모델 관련 작업을 수행하는 예제 코드가 제공되어 실습 학습을 지원합니다.
- **상세한 설명 문서:** 코드와 관련된 상세한 설명 및 주석이 제공되어 이해를 돕습니다.
- **개방형 저장소:** 누구나 자유롭게 액세스하고 활용할 수 있습니다.

### Usage

#### Installation

```
git clone https://github.com/anthropics/courses.git
```

#### Jupyter Notebook 실행

1. 저장소를 클론한 후 `courses` 디렉토리로 이동합니다.
2. `jupyter notebook` 명령을 실행합니다.
3. 브라우저에서 Jupyter Notebook 서버가 실행됩니다.
4. 원하는 Notebook 파일을 열어 학습을 시작합니다.

### Recommendation

Claude 모델을 사용하고자 하는 개발자 및 연구자에게 추천합니다. 이 저장소는 Claude SDK 사용법, 프롬프트 엔지니어링 기법 및 Claude를 활용한 도구 구현 방법을 배우는 데 유용한 자료를 제공합니다.

### External Links

- **Anthropic 웹사이트:** [https://www.anthropic.com/](https://www.anthropic.com/)
- **Claude API 문서:** [https://docs.anthropic.com/claude](https://docs.anthropic.com/claude)

### Caution

- **Claude API 키 필요:** 이 저장소의 과정을 수행하려면 Claude API 키가 필요합니다. Anthropic 웹사이트에서 무료로 API 키를 얻을 수 있습니다.
- **Python 숙련도:** 저장소의 코드는 Python으로 작성되어 있습니다. Python에 대한 기본적인 이해가 필요합니다. 
- **Claude 모델 접근 권한:** Claude 모델에 대한 접근 권한이 있어야 합니다.

## Go의 sync.Pool 활용: 메모리 효율적인 객체 재활용

### Summary

Go 언어의 `sync.Pool`은 객체를 재활용하여 메모리 할당 및 해제 비용을 줄이는 데 도움이 되는 유용한 기능입니다. 이 글에서는 `sync.Pool`의 작동 방식과 다양한 활용 사례를 소개하며, 효율적인 메모리 관리를 위한 팁을 제공합니다.

### Description

`sync.Pool`은 Go 표준 라이브러리에서 제공하는 동기화된 객체 풀입니다. 이는 빈번하게 생성 및 소멸되는 객체를 재사용함으로써 GC(Garbage Collection)에 의한 오버헤드를 줄이고, 프로그램의 성능을 향상시키는 데 도움이 됩니다.

### Discussion

1. **Sync.Pool의 작동 방식:**
    - `sync.Pool`은 객체를 풀에 저장하고 필요할 때 풀에서 가져와 재사용합니다. 
    - 풀에 객체가 없으면 새로 생성하고, 풀에 객체가 있으면 풀에서 가져와 사용합니다.
    - 객체를 풀에 반환할 때는 풀에서 사용 가능한 객체의 수가 제한되어 있습니다.

2. **Sync.Pool 사용 시 고려 사항:**
    - 객체의 크기가 작고 자주 생성 및 소멸되는 경우 `sync.Pool`을 사용하는 것이 유리합니다.
    - 객체의 상태가 변경될 수 있는 경우, 풀에서 가져온 객체의 상태를 초기화해야 합니다.
    - 객체의 수명이 짧고 GC에 의해 빠르게 해제될 경우, `sync.Pool`을 사용하는 것이 오히려 성능을 저하시킬 수 있습니다.

3. **Sync.Pool의 한계:**
    - `sync.Pool`은 객체를 재사용하기 때문에 객체의 상태가 유지됩니다. 
    - 따라서 객체의 상태를 초기화하지 않고 사용하면 예상치 못한 문제가 발생할 수 있습니다.
    - 또한, 풀에서 가져온 객체의 상태는 예측 불가능하며, 이로 인해 프로그램의 동작이 예상과 다르게 될 수 있습니다.


### Features

- **메모리 할당 및 해제 비용 절감:** 객체를 재활용하여 메모리 할당 및 해제 오버헤드를 줄입니다.
- **성능 향상:** 객체 생성 및 소멸에 소요되는 시간을 줄여 프로그램의 성능을 향상시킵니다.
- **GC 부하 감소:** `sync.Pool`을 통해 객체 재활용을 하면 GC 부하가 줄어들어 프로그램의 전체적인 성능이 향상됩니다.

### Usage

#### Installation

`sync.Pool`은 Go 표준 라이브러리에 포함되어 있으므로 별도의 설치가 필요하지 않습니다.

#### 사용 예시

```go
package main

import (
	"fmt"
	"sync"
)

// 객체를 저장할 풀 정의
var pool = sync.Pool{
	New: func() interface{} {
		return new(MyObject)
	},
}

// 객체 구조체 정의
type MyObject struct {
	// 객체의 데이터
}

func main() {
	// 풀에서 객체 가져오기
	obj := pool.Get().(*MyObject)
	fmt.Println(obj)

	// 객체 사용 후 풀에 반환
	pool.Put(obj)
}
```

####  `sync.Pool` 활용 시 유의 사항

- `New` 함수는 `sync.Pool`에 객체가 없을 때 호출되어 새로운 객체를 생성합니다.
- `Get` 함수는 풀에서 객체를 가져오고, 풀에 객체가 없으면 `New` 함수를 호출하여 새로운 객체를 생성합니다.
- `Put` 함수는 풀에 객체를 반환합니다.
- `sync.Pool`에 반환된 객체는 다시 풀에서 가져와 재사용됩니다.

### Recommendation

`sync.Pool`은 객체를 재활용하여 메모리 효율성을 높이는 데 유용한 기능입니다. 특히 객체의 크기가 작고 자주 생성 및 소멸되는 경우 `sync.Pool`을 사용하는 것이 효과적입니다.

### External Links

- [Go 문서: sync.Pool](https://pkg.go.dev/sync#Pool)
- [Go Blog: Sync.Pool in Go](https://go.dev/blog/sync-pool)

### Caution

- `sync.Pool`은 객체의 상태를 유지하기 때문에, 객체의 상태를 초기화하지 않고 사용하면 예상치 못한 문제가 발생할 수 있습니다.
- `sync.Pool`은 Go의 GC와 함께 사용됩니다. 따라서 `sync.Pool`에서 객체를 가져와 사용할 때는 GC에 의해 객체가 해제되지 않도록 주의해야 합니다.
- 객체의 수명이 짧고 GC에 의해 빠르게 해제될 경우, `sync.Pool`을 사용하는 것이 오히려 성능을 저하시킬 수 있습니다.

## Encore.ts: Express.js보다 9배 빠르고 Bun보다 3배 빠른 Zod 기반 웹 프레임워크

### 요약

이 글은 타입스크립트 기반 오픈소스 백엔드 프레임워크인 Encore.ts를 소개합니다. Encore.ts는 Express.js와 Bun보다 훨씬 빠른 성능을 제공하며, Zod를 사용하여 강력한 타입 안전성을 보장합니다.

### 설명

Encore.ts는 Express.js와 유사한 API를 제공하면서도 뛰어난 성능과 타입 안전성을 제공하는 Node.js 웹 프레임워크입니다. Zod를 통해 입력 및 출력 데이터를 검증하여 런타임 오류를 방지하고 코드 신뢰성을 높입니다.

### 토론

1. **Encore.ts의 성능:** Encore.ts는 Express.js보다 9배, Bun보다 3배 빠른 성능을 자랑합니다. 이는 Zod 기반 타입 검사와 효율적인 코드 구조 덕분입니다.
2. **타입 안전성:** Encore.ts는 Zod를 사용하여 타입 검사를 강제하여 개발 중에 오류를 조기에 발견하고 코드의 신뢰성을 높일 수 있습니다.
3. **Express.js와의 호환성:** Encore.ts는 Express.js와 유사한 API를 제공하여 Express.js 개발자라면 쉽게 전환할 수 있습니다.

### 기능

- Zod 기반 타입 검사 시스템
- Express.js와 유사한 API
- 고성능 웹 서버
- 미들웨어 지원

### 사용

#### 설치

```bash
npm install encore
```

#### 기본 사용

```javascript
import { createApp } from 'encore';

const app = createApp();

app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(3000, () => {
  console.log('Server is listening on port 3000');
});
```

#### 라우팅

```javascript
import { createApp, Router } from 'encore';

const app = createApp();
const router = new Router();

router.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.use(router);

app.listen(3000, () => {
  console.log('Server is listening on port 3000');
});
```

### 추천

- Node.js 기반 웹 애플리케이션 개발에 새로운 프레임워크를 찾는 개발자
- 성능과 타입 안전성이 중요한 프로젝트
- Express.js 개발 경험이 있는 개발자

### 외부 링크

- [Encore GitHub 저장소](https://github.com/encorejs/encore)
- [Encore 문서](https://encorejs.com/docs)

### 주의

- Encore.ts는 아직 개발 초기 단계이며 일부 기능이 완벽하게 구현되지 않았을 수 있습니다.
- Zod에 대한 기본적인 이해가 필요합니다.

## ONNX 모델을 사용한 음성 인식 시스템 구축: SenseVoice

### 요약

Sherpa Sense Voice는 ONNX 모델을 사용하여 음성 인식 시스템을 구축하는 오픈소스 프로젝트입니다. 이 프로젝트는 다양한 음성 인식 모델을 ONNX 형식으로 변환하고, 이를 사용하여 실시간 음성 인식, 음성 텍스트 변환, 음성 검색 등의 기능을 구현할 수 있도록 지원합니다. 

### 설명

Sherpa Sense Voice는 ONNX 모델을 사용하여 음성 인식 시스템을 구축하는 데 필요한 모든 구성 요소를 제공합니다. 여기에는 ONNX 모델 변환 도구, 음성 인식 파이프라인, 예제 코드 및 문서가 포함됩니다. 이 프로젝트는 개발자들이 ONNX 모델을 사용하여 음성 인식 시스템을 쉽게 구축하고 사용할 수 있도록 설계되었습니다.

### 토론

1. **다양한 ONNX 모델 지원**: Sherpa Sense Voice는 다양한 음성 인식 모델을 지원하며, 이를 통해 개발자는 자신의 요구 사항에 맞는 모델을 선택할 수 있습니다.
2. **실시간 음성 인식**: Sherpa Sense Voice는 실시간 음성 인식 기능을 제공하여 사용자의 음성을 실시간으로 처리할 수 있습니다.
3. **음성 텍스트 변환**: Sherpa Sense Voice는 음성을 텍스트로 변환하는 기능을 제공하여 음성 인식 결과를 텍스트 형식으로 사용할 수 있도록 합니다.

### 기능

- ONNX 모델 변환 도구
- 음성 인식 파이프라인
- 예제 코드 및 문서

### 추천

Sherpa Sense Voice는 ONNX 모델을 사용하여 음성 인식 시스템을 구축하려는 개발자들에게 유용한 프로젝트입니다. 이 프로젝트는 사용하기 쉽고, 다양한 기능을 제공하며, 다양한 ONNX 모델을 지원합니다.

### 외부 링크

- [Sherpa Sense Voice GitHub 저장소](https://k2-fsa.github.io/sherpa/onnx/sense-voice/index.html)
- [FunAudioLLM SenseVoice 저장소](https://github.com/FunAudioLLM/SenseVoice)

### 주의

- ONNX 모델을 사용하기 전에 모델의 라이선스 조건을 확인해야 합니다.
- Sherpa Sense Voice는 개발 단계에 있으며, 일부 기능은 아직 완벽하게 구현되지 않았을 수 있습니다.

## 임베딩의 코사인 유사도가 정말 유사성을 나타낼까요?

### 요약

본 논문은 임베딩 벡터 간의 코사인 유사도가 실제로 의미 있는 유사성을 나타내는지에 대한 의문을 제기합니다. 코사인 유사도는 두 벡터 간의 각도의 코사인 값으로, 일반적으로 고차원 데이터의 의미적 유사성을 측정하는 데 사용됩니다. 저자들은 정규화된 선형 모델에서 도출된 임베딩을 분석하여 코사인 유사도가 임의적이고 의미 없는 유사성을 산출할 수 있음을 분석적으로 보여줍니다. 또한, 딥 러닝 모델 학습 시 다양한 정규화 기법이 사용되는데, 이러한 정규화 기법은 임베딩의 코사인 유사도에 숨겨진 영향을 미쳐 결과를 불투명하게 만들고 임의성을 야기할 수 있다고 설명합니다. 따라서 저자들은 임베딩의 코사인 유사도를 무분별하게 사용하는 것에 대한 주의를 촉구하고, 대안적인 유사성 측정 방법을 제시합니다.

### Description

임베딩은 고차원 데이터를 저차원 벡터 공간으로 매핑하여 의미적 유사성을 측정하는 데 사용됩니다. 코사인 유사도는 두 벡터 간의 각도의 코사인 값으로, 일반적으로 임베딩 벡터 간의 의미적 유사성을 측정하는 데 사용됩니다. 즉, 두 벡터가 유사할수록 코사인 유사도 값은 1에 가까워지고, 두 벡터가 다를수록 코사인 유사도 값은 0에 가까워집니다.

하지만 본 논문은 코사인 유사도가 실제로 의미 있는 유사성을 나타내는지에 대한 의문을 제기합니다. 저자들은 정규화된 선형 모델에서 도출된 임베딩을 분석하여 코사인 유사도가 임의적이고 의미 없는 유사성을 산출할 수 있음을 분석적으로 보여줍니다. 즉, 코사인 유사도 값이 높다고 해서 두 벡터가 실제로 의미적으로 유사하다고 할 수 없다는 것입니다.

### Discussion

1. **코사인 유사도의 한계:** 본 논문은 코사인 유사도가 임베딩 벡터 간의 의미적 유사성을 측정하는 데 적합하지 않을 수 있음을 보여줍니다. 코사인 유사도는 벡터의 크기 정보를 무시하고 각도만 고려하기 때문에, 크기가 다른 벡터 간의 유사성을 정확하게 측정할 수 없습니다. 
2. **정규화의 영향:** 딥 러닝 모델 학습 시 사용되는 다양한 정규화 기법은 임베딩의 코사인 유사도에 숨겨진 영향을 미쳐 결과를 불투명하게 만들 수 있습니다. 즉, 정규화 기법이 임베딩 벡터의 크기에 영향을 미치면서 코사인 유사도 값에 영향을 주기 때문에, 코사인 유사도 값이 정확한 의미적 유사성을 나타내지 못할 수 있습니다.
3. **대안적인 유사성 측정 방법:** 저자들은 코사인 유사도 대신 다른 유사성 측정 방법을 사용할 것을 권장합니다. 예를 들어, 유클리드 거리, 맨하탄 거리 등을 사용할 수 있으며, 이러한 방법들은 벡터의 크기 정보를 고려하여 더 정확한 유사성을 측정할 수 있습니다.

### Features

- 코사인 유사도의 문제점을 분석적으로 증명
- 딥 러닝 모델 학습 시 정규화의 영향에 대한 분석
- 코사인 유사도 대신 사용할 수 있는 대안적인 유사성 측정 방법 제시

### Recommendation

본 논문은 임베딩의 코사인 유사도에 대한 새로운 시각을 제공하며, 딥 러닝 모델 학습 및 유사성 측정 시 유용한 정보를 제공합니다. 연구자들은 본 논문을 통해 코사인 유사도의 한계를 인식하고, 더 정확한 유사성 측정 방법을 선택하여 연구를 진행할 수 있습니다.

### External Links

- 논문 원문: [https://arxiv.org/abs/2403.05440](https://arxiv.org/abs/2403.05440)

### Caution

- 본 논문에서 제시된 분석은 정규화된 선형 모델에 기반한 것이며, 모든 딥 러닝 모델에 일반화될 수는 없습니다.
- 코사인 유사도는 여전히 유사성을 측정하는 데 유용한 방법이 될 수 있지만, 무분별하게 사용하는 것은 위험할 수 있습니다. 따라서 코사인 유사도를 사용하기 전에 데이터 특성과 모델 학습 과정을 고려하여 신중하게 판단해야 합니다.

## Retrieval Augmented Generation 또는 Long-Context LLM? 포괄적인 연구 및 하이브리드 접근 방식

### Summary

이 논문은 대규모 언어 모델(LLM)이 지나치게 긴 맥락을 효율적으로 처리할 수 있도록 하는 강력한 도구인 검색 증강 생성(RAG)과 최근 Gemini-1.5 및 GPT-4와 같은 LLM이 보여주는 긴 맥락을 직접 이해하는 뛰어난 능력을 비교 분석합니다. 이 논문은 두 기술의 장점을 활용하기 위해 RAG와 긴 맥락(LC) LLM 간의 포괄적인 비교를 수행합니다.

### Description

이 논문은 세 가지 최신 LLM을 사용하여 다양한 공개 데이터 세트에서 RAG와 LC를 벤치마킹하여 RAG와 LC를 비교 분석합니다. 그 결과, LC는 충분한 리소스가 제공될 때 평균 성능 측면에서 RAG를 지속적으로 능가한다는 사실이 밝혀졌습니다. 그러나 RAG의 상당히 낮은 비용은 여전히 ​​뚜렷한 장점입니다. 이러한 관찰을 바탕으로 모델 자기 반성을 기반으로 쿼리를 RAG 또는 LC로 라우팅하는 간단하면서도 효과적인 방법인 Self-Route를 제안합니다. Self-Route는 LC와 비교할 수 있는 성능을 유지하면서 계산 비용을 크게 줄입니다.

### Discussion

1. **RAG와 LC의 장단점 비교**: RAG는 LC보다 효율적이지만 성능이 떨어질 수 있습니다. 반면 LC는 RAG보다 성능이 뛰어나지만 비용이 더 많이 들 수 있습니다.
2. **Self-Route의 장점**: Self-Route는 쿼리의 복잡성을 평가하고 적합한 모델(RAG 또는 LC)로 라우팅하여 성능과 비용 간의 균형을 맞춥니다.
3. **긴 맥락 애플리케이션에 대한 지침**: 이 논문은 RAG와 LC를 사용하는 LLM의 긴 맥락 애플리케이션에 대한 지침을 제공합니다.

### Features

- **RAG와 LC의 포괄적인 비교 분석**: RAG와 LC를 다양한 데이터 세트와 LLM을 사용하여 벤치마킹합니다.
- **Self-Route의 제안**: 쿼리를 RAG 또는 LC로 라우팅하는 새로운 하이브리드 접근 방식을 제안합니다.
- **긴 맥락 애플리케이션에 대한 지침**: RAG와 LC를 사용하는 LLM의 긴 맥락 애플리케이션에 대한 지침을 제공합니다.

### Usage

#### 설치

```bash
pip install transformers
pip install datasets
```

#### 코드 생성

```python
from transformers import AutoModelForSeq2SeqLM, AutoTokenizer

model_name = "facebook/bart-large-cnn"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSeq2SeqLM.from_pretrained(model_name)

text = "Python으로 숫자를 더하는 함수를 만들어주세요."
inputs = tokenizer(text, return_tensors="pt")
outputs = model.generate(**inputs)

decoded_output = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(decoded_output)
```

### Recommendation

이 논문은 RAG와 LC 간의 포괄적인 비교를 제공하고 긴 맥락 애플리케이션에 대한 귀중한 통찰력을 제공합니다. LLM 기반 긴 맥락 작업을 수행하는 연구자에게 유용한 자료입니다.

### External Links

- [arXiv 논문 링크](https://arxiv.org/abs/2407.16833)
- [Hugging Face 모델 페이지](https://huggingface.co/facebook/bart-large-cnn)

### Caution

- **모델 선택**: RAG 또는 LC를 사용할지 여부는 특정 애플리케이션의 요구 사항과 제약 조건에 따라 결정해야 합니다.
- **Self-Route 구현**: Self-Route는 복잡한 쿼리에 대해 LC를 사용하고 간단한 쿼리에 대해 RAG를 사용하는 것과 같은 특정 애플리케이션에 적응해야 합니다.

## 주의

 - 이 글은 Gemini Flash를 이용하여 생성한 것으로, 사실과 다를 수 있습니다.

## 출처

 - [https://www.bleuio.com/blog/building-ble-applications-with-bleuio-and-go](https://www.bleuio.com/blog/building-ble-applications-with-bleuio-and-go)
 - [https://github.com/adalkiran/llama-nuts-and-bolts](https://github.com/adalkiran/llama-nuts-and-bolts)
 - [https://github.com/palantir/goastwriter](https://github.com/palantir/goastwriter)
 - [https://github.com/janpfeifer/gonb](https://github.com/janpfeifer/gonb)
 - [https://kmcd.dev/posts/fauxrpc/](https://kmcd.dev/posts/fauxrpc/)
 - [https://blog.zomato.com/go-beyond-building-performant-and-reliable-golang-applications](https://blog.zomato.com/go-beyond-building-performant-and-reliable-golang-applications)
 - [https://github.com/Broderick-Westrope/tetrigo](https://github.com/Broderick-Westrope/tetrigo)
 - [https://words.filippo.io/dispatches/ml-kem-seeds/](https://words.filippo.io/dispatches/ml-kem-seeds/)
 - [https://github.com/knights-analytics/hugot](https://github.com/knights-analytics/hugot)
 - [https://github.com/gomlx/gomlx](https://github.com/gomlx/gomlx)
 - [https://github.com/facebookincubator/sks](https://github.com/facebookincubator/sks)
 - [https://docs.kernel.org/networking/tls-offload.html](https://docs.kernel.org/networking/tls-offload.html)
 - [https://github.com/Permify/permify](https://github.com/Permify/permify)
 - [https://dev.to/marscode/golang-security-review-guide-4kk5](https://dev.to/marscode/golang-security-review-guide-4kk5)
 - [https://github.com/jpillora/chisel](https://github.com/jpillora/chisel)
 - [https://github.com/anthropics/courses](https://github.com/anthropics/courses)
 - [https://victoriametrics.com/blog/go-sync-pool/index.html](https://victoriametrics.com/blog/go-sync-pool/index.html)
 - [https://dev.to/encore/encorets-9x-faster-than-expressjs-3x-faster-than-bun-zod-4boe](https://dev.to/encore/encorets-9x-faster-than-expressjs-3x-faster-than-bun-zod-4boe)
 - [https://k2-fsa.github.io/sherpa/onnx/sense-voice/index.html](https://k2-fsa.github.io/sherpa/onnx/sense-voice/index.html)
 - [https://arxiv.org/abs/2403.05440](https://arxiv.org/abs/2403.05440)
 - [https://arxiv.org/abs/2407.16833](https://arxiv.org/abs/2407.16833)

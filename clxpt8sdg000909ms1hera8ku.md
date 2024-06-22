---
title: "Go 언어 뉴스레터: //go:linkname 사용 제한에 대한 논의"
datePublished: Sat Jun 22 2024 07:40:36 GMT+0000 (Coordinated Universal Time)
cuid: clxpt8sdg000909ms1hera8ku
slug: go-golinkname
tags: newsletter

---

> 이 기사는 Gemini를 이용해 작성된 것입니다.

## 토론

1. Go 표준 라이브러리 내부(특히 런타임 내부)에 접근하기 위해 `//go:linkname`을 과도하게 사용하면 Go 생태계의 많은 패키지에 의존하는 패키지가 표준 라이브러리 내부를 변경할 때 문제가 발생할 수 있습니다. 예를 들어, <a href="https://go.dev/cl/583756" rel="nofollow">https://go.dev/cl/583756</a>는 github.com/goccy/go-json이 런타임의 내부 타입 API를 대부분 복사했기 때문에 해당 패키지를 깨뜨렸습니다. 
2. 이러한 상황은 지속 가능하지 않습니다. 내부는 이유가 있어 내부로 유지됩니다. Go 프로그램이 내부 세부 정보에 대한 명시적 종속성을 만들 수 있도록 허용하는 것은 Go 프로그램의 작동을 유지할 수 없게 만듭니다. 
3. 이 문제는 `//go:linkname` 기반 종속성을 방지하고 기존 종속성을 제한하기 위한 작업을 추적합니다.

## 요약

- `//go:linkname`을 사용한 Go 프로그램이 표준 라이브러리 내부에 대한 종속성을 만드는 것을 방지하는 것이 목표입니다.
- 이를 위해 `-checklinkname=1` 플래그를 도입하여 표준 라이브러리의 기호에 대해 핸드셰이크 형식을 요구합니다.
- 이 플래그는 Go 1.23에서 기본값으로 설정될 예정입니다.

## 외부 링크

- <a href="https://go.dev/cl/583756" rel="nofollow">https://go.dev/cl/583756</a>
- <a href="https://github.com/goccy/go-json/blob/9b91208837a56bcf74bd65cce368ee3911ae7d03/internal/runtime/rtype.go">https://github.com/goccy/go-json/blob/9b91208837a56bcf74bd65cce368ee3911ae7d03/internal/runtime/rtype.go</a>
- <a href="https://deps.dev/go/github.com%2Fgoccy%2Fgo-json/v0.10.2/dependents" rel="nofollow">https://deps.dev/go/github.com%2Fgoccy%2Fgo-json/v0.10.2/dependents</a>

## 주의

이 문서는 Gemini flash 모델에 의해 작성되었습니다. 오류가 포함될 수 있습니다.

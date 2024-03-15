---
title: "24년 3월 전반기 뉴스레터"
datePublished: Fri Mar 15 2024 20:55:07 GMT+0000 (Coordinated Universal Time)
cuid: cltt517xp00020ajvf65jgh6f
slug: 24-3
tags: newsletter

---

## 강력하고 빠른 우선 순위 큐!

디스크 백업 기능이 포함된!

필요하십니까?

[JustinTimperio/gpq: GPQ is a high performance embeddable double priority queue with complex priority ordering guarantees (github.com)](https://github.com/JustinTimperio/gpq)

---

## 고 프로그램에 내장시킬 수 있는 분산 캐시 라이브러리는 어떤가요?

레디스를 두는 의미가 퇴색되는 건 아니지만, 데이터의 실시간 정합성이 중요한 케이스가 아니라면 충분히 유용할 것으로 기대됩니다.

[buraksezer/olric: Distributed in-memory object store. It can be used as an embedded Go library and a language-independent service. (github.com)](https://github.com/buraksezer/olric)

[EchoVault/EchoVault: Distributed in-memory data store with an emphasis on speed and reliability. (github.com)](https://github.com/EchoVault/EchoVault)

---

## 자기만의 미디어 라이브러리 갖고 싶지 않나요?

전 과거 Lux라는 웹 라이브러리 셋을 구성할 때, 미디어도 서빙할 수 있는 기능을 추가하고 싶었습니다.

그때 생각해보니 저장이나 다른 무언가에 대한 대비가 하나도 안 되어 있었네요.

그런 저 같은 사람들을 위한 솔루션!

[zoriya/Kyoo: A portable and vast media library solution. (github.com)](https://github.com/zoriya/Kyoo)

---

## 고에 드디어 QUIC가 std로!

들어옵니다.

[quic package - golang.org/x/net/quic - Go Packages](https://pkg.go.dev/golang.org/x/net/quic)

---

## 이미 고에는 엑셀을 편집할 수 있는 라이브러리가 있습니다.

하지만 docx도 있으면 더 유용하겠군요.

[gomutex/godocx: Go library for reading and writing Microsoft Docx (github.com)](https://github.com/gomutex/godocx)

[qax-os/excelize: Go language library for reading and writing Microsoft Excel™ (XLAM / XLSM / XLSX / XLTM / XLTX) spreadsheets (github.com)](https://github.com/qax-os/excelize)

---

## 고에서 다른 언어 가져와 쓰기

WASM을 끼얹은

[tetratelabs/wazero: wazero: the zero dependency WebAssembly runtime for Go developers (github.com)](https://github.com/tetratelabs/wazero)

---

## 최근 추가된 제네릭 슬라이스 패키지에 대해 얼마나 알고 계신 가요?

[Robust generic functions on slices - The Go Programming Language](https://go.dev/blog/generic-slice-functions)

---

## sqlc, 좋은 툴입니다, 그쳐?

postgres도 섹시한 DB구요.

go도 훌륭한 언어입니다.

[Go application setup with PostgreSQL, sqlx, goose migrations - YouTube](https://www.youtube.com/watch?v=AeIksLEHp8E)

---

## 저는 필드를 좀 더 제대로 보고 싶습니다

마치 프로그램에 X-ray라도 찍은 듯이요.

[yassinebenaid/godump: Go library to dump variables and data structures. (github.com)](https://github.com/yassinebenaid/godump)

---

## postgresql을 이용할 때 장애 대응을 어떻게 하시나요?

저는 RDB는 레플리케이션 외에는 그다지 좋은 선택지가 막 떠오르진 않습니다.

샤딩도 장애로부터 데이터를 완전히 보호하는 것과는 거리가 있는 선택지니까요.

[Writing a Postgres Logical Replication System in Golang | DoltHub Blog](https://www.dolthub.com/blog/2024-03-08-postgres-logical-replication/)

---

## 데이터 전송을 위한 객체의 스펙은 명시적이야 합니다

이 분야에서 가장 유명한 건 프로토콜 버퍼라고 생각합니다.

그리고 잘 안 쓰이지만 뒤이어 등장한 플랫버퍼같은 게 존재하죠.

또 다른 선택지인 karmen이나 bebop은 또 어떨까요?

[Protocol Buffers Documentation (protobuf.dev)](https://protobuf.dev/)

[FlatBuffers: FlatBuffers](https://flatbuffers.dev/)

[inkeliz/karmem: Karmem is a fast binary serialization format, faster than Google Flatbuffers and optimized for TinyGo and WASM. (github.com)](https://github.com/inkeliz/karmem)

[Bebop](https://bebop.sh/)

---

## 아마도 저는 B 트리이어야 합니다,

아님 말고.

[Prolly Trees | DoltHub Blog](https://www.dolthub.com/blog/2024-03-03-prolly-trees/)

---

## EdgeDB라고 아시나요?

그거 말고, postgres 위에 구성된 그래프 형태의 데이터베이스입니다.

EdgeQL이랑 독자적인 쿼리 언어를 가지고 있으며, 이 언어는 예전 SQL도 잘 모르던 저 조차도 DB를 다룰 수 있게 해준 친절한 친구입니다.

[EdgeDB | The post-SQL era has arrived](https://www.edgedb.com/)

---

## message queue, 하지만 postgres를 베이스로 한.

postgres만 있으면 그렇게 고성능과 안정성이 필요하지 않다면, nats와 kafka 대신 간단하게 구성해 보는 건 어떤가요??

[Devious SQL: Message Queuing Using Native... | Crunchy Data Blog](https://www.crunchydata.com/blog/message-queuing-using-native-postgresql)

[LISTEN & NOTIFY 명령으로 구현하는 비동기식 작업: 한국 포스트그레스큐엘 홈페이지 (postgresql.kr)](https://postgresql.kr/blog/pg_listen_notify.html)

---

## 시스템 콜을 이용해서 더 빠른 패킷 전송 구현 하기

[High-Speed Packet Transmission in Go: From net.Dial to AF\_XDP (toonk.io)](https://toonk.io/sending-network-packets-in-go/index.html)

---

## Go 1.22에 for range에 올릴 수 있는 함수 스펙이 정의 되었습니다

아직 실험적 단계에 지나지 않지만, 머지 않아 알아야 할 수 있으니 배워 볼까요?

[Exploring Go's Functional Iterators (Range-over Functions) | Perfects.Engineering Blog](https://blog.perfects.engineering/go_range_over_funcs)

---

## 고에는 사실 매우 성능이 좋은 웹 프레임워크가 있습니다

근데 중국에서 만든 거 아니냐 구요?

걱정 되면 오픈소스니까 검사하고 쓰시면 되죠.

[gnet - A high-performance, lightweight, non-blocking, event-driven networking framework written in pure Go | gnet](https://gnet.host/)

---

## 더 확실한 추적을 위해!

[More powerful Go execution traces - The Go Programming Language](https://go.dev/blog/execution-traces-2024)

---

## OpenAPI를 생성하는 웹 프레임워크

[go-fuego/fuego: Golang Fuego - web framework generating OpenAPI 3 spec from source code (github.com)](https://github.com/go-fuego/fuego?utm_source=pocket_saves)

---

## Go 1.22에는 라우팅 관련 기능도 추가되었습니다

서드파티에게 큰 위협이에요.

[Routing Enhancements for Go 1.22 - The Go Programming Language](https://go.dev/blog/routing-enhancements?utm_source=pocket_saves)

---

## 노션과 옵시디언, 좋다고 생각합니다.

전 못 쓰지만요.

[Logseq: A privacy-first, open-source knowledge base](https://logseq.com/)

[zadam/trilium: Build your personal knowledge base with Trilium Notes (github.com)](https://github.com/zadam/trilium?utm_source=pocket_saves)

[Outline – Team knowledge base & wiki (getoutline.com)](https://www.getoutline.com/)

---

## Super Fast Web Framework in Zig

[zigzap/zap: blazingly fast backends in zig (github.com)](https://github.com/zigzap/zap)
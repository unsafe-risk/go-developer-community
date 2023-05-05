---
title: "23년 4월 두번째 뉴스레터"
datePublished: Wed May 03 2023 13:50:43 GMT+0000 (Coordinated Universal Time)
cuid: clh7raehx00040al4hmrc6nzn
slug: 23-4
tags: newsletter

---

### **Sqlite는 장난감이 아니다!**

Anton Zhiyanov는 자신의 블로그에 sqlite에 대한 아티클을 기고했습니다.  
Sqlite가 단순한 작은 데이터베이스가 아니라는 걸 어필합니다.  
이어서 개발자, 데이터 분석가, QA, 데브옵스, PM에게 훌륭한 도구라고 합니다.  
IT 엔지니어링에 밀접한 직업이라면 한번 읽어보는 게 어떨까요??

[SQLite is not a toy database (](https://antonz.org/sqlite-is-not-a-toy-database/)[antonz.org](http://antonz.org)[)](https://antonz.org/sqlite-is-not-a-toy-database/)  

---

### **예쁜 TUI 한번 만들어 보실?**

콘솔 화면에서 작업의 대기, 진척도, 완료 여부 등을 나타내는 UI가 있습니다.  
전 한번씩 그런걸 만들어 보고 싶기는 한데, 콘솔에 예술을 할 자신이 없어서 항상 포기했습니다 ㅠ  
이번에 소개해 드릴 아티클은 바로 저같은 사람들을 위한!  
버블티 라이브러리를 활용해 만들어보는 튜토리얼같은 문서입니다.

[The Bubbletea (TUI) State Machine pattern - Zachary Proser (](https://www.zackproser.com/blog/bubbletea-state-machine)[zackproser.com](http://zackproser.com)[)](https://www.zackproser.com/blog/bubbletea-state-machine)  
[charmbracelet/bubbletea: A powerful little TUI framework 🏗 (](https://github.com/charmbracelet/bubbletea)[github.com](http://github.com)[)](https://github.com/charmbracelet/bubbletea)

---

### **발전한 타입의 템플릿 엔진**

이전에 한번 소개해드린 적 있는 a-h의 templ이 더욱 발전했습니다.  
얼마 전에 0.2.282 버전을 릴리즈 했는데요.  
못 보던 사이에 공식 문서도 생기고, 템플릿을 만드는데 편리한 기능들이 몇 추가되었습니다!

[Introduction | templ docs](https://templ.guide/)  
[Release v0.2.282 · a-h/templ (](https://github.com/a-h/templ/releases/tag/v0.2.282)[github.com](http://github.com)[)](https://github.com/a-h/templ/releases/tag/v0.2.282)

---

### **JSON을 섹시하게 생성하는 방법**

json을 만들 때, 혹시 한번씩 상속이나 템플릿처럼 사용하고 싶은 부분이 있지 않나요?  
jsonnet은 그런 상황에 맞추어 만들어진 시스템입니다!  
jsonnet을 사용하면 특정 json과 필드를 템플릿처럼 활용할 수 있으며, 필요에 따라 변수를 사용하여 일부분을 대치하여 사용할 수도 있습니다.

[Jsonnet - Jsonnet Configuration Language](https://jsonnet.org/)  
[google/go-jsonnet (](https://github.com/google/go-jsonnet)[github.com](http://github.com)[)](https://github.com/google/go-jsonnet)

---

### **The Making of an Ultra Low Latency Trading System with Go and Java**

저는 사실 가상 화폐 거래에 대해 잘 알지 못 합니다.  
하지만 분명 가상 화폐 거래에는 적지 않은 컴퓨팅 자원이 들 것입니다.  
그런 부분을 C++이나 러스트가 아니라 고와 자바를 통해 저지연 시스템을 만드는 건 꽤 흥미로운 부분입니다.  
어떤 이야기가 오고 갔을 지 궁금하시면 다음 영상을 시청해 보세요!

[https://youtu.be/6SXd0cNRVN8](https://youtu.be/6SXd0cNRVN8)

---

### **당근!**

당근마켓은 국내 기업 중 고 언어 라이브러리를 꾸준히 공개하는 곳입니다.  
최근에 웹사이트를 깃헙에 풀어버려서 프론트 쪽에도 한번 충격을 준 적이 있죠.  
그런 당근마켓의 몇가지 고 언어 라이브러리를 소개해드리려고 합니다.

1. gorean은 한글 처리를 위한 라이브러리로, 다양한 편의 기능을 제공합니다.
    
2. genequal은 코드 생성기를 활용한 비교 연산 생성 라이브러리로, 사실상의 deep equal을 구현합니다.
    
3. autopprof는 주기적으로 CPU와 메모리 사용량을 수집하여 임계점을 넘을 경우 조직 구성원에게 경고를 주는 기능을 제공합니다.
    
4. 마지막으로 minimemcached는 memcached의 고 언어 구현입니다. 멤캐시드를 사용하는 고 프로젝트의 유닛테스트를 위한 구현입니다.
    

다른 기업들도 고 언어 라이브러리를 오픈소스로 공개하겠지만, 더 많은 고를 사용하는 기업들이 여유가 될 때 하나씩 공개해주면 매우 감사할 것같습니다.

[daangn/gorean: korean analyzer utility tools (](https://github.com/daangn/gorean)[github.com](http://github.com)[)](https://github.com/daangn/gorean)    
[daangn/genequal: Generate Equal() methods from AST (](https://github.com/daangn/genequal)[github.com](http://github.com)[)](https://github.com/daangn/genequal)  
[daangn/autopprof: Automatically profile the Go applications when CPU or memory utilization crosses threshold (](https://github.com/daangn/autopprof)[github.com](http://github.com)[)](https://github.com/daangn/autopprof)  
[daangn/minimemcached: Pure Go memcached server for Go unittests motivated by miniredis (](https://github.com/daangn/minimemcached)[github.com](http://github.com)[)](https://github.com/daangn/minimemcached)

---

### **더 크고 빠른 인 메모리 캐시가 필요하신가요?**

지난번에 ristretto를 소개해드린 적이 있습니다.  
리스트레토도 분명 좋은 인 메모리 캐시 라이브러리입니다.  
하지만 지금 소개해드릴 theine-go는 리스트레토보다 좋은 벤치마크 결과를 내세우고 있습니다.  
한번 진짜 좋은 지 지켜볼까요?

[Yiling-J/theine-go: high performance in-memory cache (](https://github.com/Yiling-J/theine-go)[github.com](http://github.com)[)](https://github.com/Yiling-J/theine-go)

---

### **귀찮은 작업 대신 해드렸습니다.**

gookit은 여러가지 프레임워크와 라이브러리를 제공합니다.  
정말 다양한 내용의 것들이 존재하니, 한번 문서를 보고 원하시는 게 있는 지 아이쇼핑 해보는 건 어떨까요?

[GCli - command-line application and tool library written in Golang. (](https://gookit.github.io/#/)[gookit.github.io](http://gookit.github.io)[)](https://gookit.github.io/#/)  
[gookit/goutil: 💪 Helper Utils(600+): int, byte, string, array/slice, map, struct, dump, convert/format, error, web/http, cli/flag, OS/ENV, filesystem, system, test/assert, time and more. Go 常用的一些工具函数：数字，字符串，数组，Map，结构体，反射，文本，文件，错误，时间日期，特殊处理，格式化，常用信息获取等等 (](https://github.com/gookit/goutil)[github.com](http://github.com)[)](https://github.com/gookit/goutil)
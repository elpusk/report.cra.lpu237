# report.cra.lpu237
lpu237 device CRA(Cyber Resilience Act) 대응 자료

- 이 repo 는 lpu237 device의 CRA 대응을 정리한 자료를 관리 목적
- CRA 는 2024.10.01 부로 발효된 EU의 사이버보안 규제
- CRA 의 제 14조 신고 의무는 2026.9.11 부터 적용
- CRA 는 2027.12.11 부터 전면 적용

## 제품 분류
- lpu237 은 결제 시스템에 사용되지 않고, 회원 카드에 기록돤 마그네틱 정보를 PC에 단순 전송하는 기능을 담당하므로 기본 클래스에 포함 되어야 한다.

## CRA 전면 적용를 위한 문서

1. 각 요소 SBOM
  - [SBOM 이 포함된 최신 firmware](https://github.com/elpusk/public.lpu237.firmware/blob/9627c35963c037aa0a33cb53581314afc017727b/lpu23x/lpu23x_00038_sbom.zip)
  - 기본 SBOM
    - [win.full.x64.cyclonedx](https://github.com/elpusk/public.lpu237.software/blob/main/full/x64/lp230-x64-wix-sbom-cyclonedx.json)
    - [win.full.x64.spdx](https://github.com/elpusk/public.lpu237.software/blob/main/full/x64/lp230-x64-wix-sbom-spdx.json)
    - [win.full.x86.cyclonedx](https://github.com/elpusk/public.lpu237.software/blob/main/full/x86/lp230-wix-sbom-cyclonedx.json)
    - [win.full.x86.spdx](https://github.com/elpusk/public.lpu237.software/blob/main/full/x86/lp230-wix-sbom-spdx.json)
    - [win.mapperonly.x64.cyclonedx](https://github.com/elpusk/public.lpu237.software/blob/main/mapper_only/x64/lp237-mapper-only-x64-wix-sbom-cyclonedx.json)
    - [win.mapperonly.x64.spdx](https://github.com/elpusk/public.lpu237.software/blob/main/mapper_only/x64/lp237-mapper-only-x64-wix-sbom-spdx.json)
    - [win.mapperonly.x86.cyclonedx](https://github.com/elpusk/public.lpu237.software/blob/main/mapper_only/x86/lpu237-mapper-only-wix-sbom-cyclonedx.json)
    - [win.mapperonly.x86.spdx](https://github.com/elpusk/public.lpu237.software/blob/main/mapper_only/x86/lpu237-mapper-only-wix-sbom-spdx.json)
    - [win.msronly.x86.cyclonedx](https://github.com/elpusk/public.lpu237.software/blob/main/msr_only/x86/lp230-msr-only-wix-sbom-cyclonedx.json)
    - [win.msronly.x86.spdx](https://github.com/elpusk/public.lpu237.software/blob/main/msr_only/x86/lp230-msr-only-wix-sbom-spdx.json)
  - Android Mapper SBOM
    - [cyclonedx type](https://github.com/elpusk/device.lpu237_adr/blob/master/apk/app-release-unsigned-sbom-cyclonedx.json)
    - [spdx type](https://github.com/elpusk/device.lpu237_adr/blob/master/apk/app-release-unsigned-sbom-spdx.json)


## 2026.09.11 부터 적용 되는 의무

**핵심: 취약점·사고 "보고 의무"(Article 14)가 시작됩니다**

CRA(Regulation (EU) 2024/2847)는 2024년 12월 10일 발효되었고, 대부분의 의무는 2027년 12월 11일부터 전면 적용되지만, 가장 부담이 큰 조항 중 하나인 Article 14의 의무적 취약점 및 사고 보고 의무는 2026년 9월 11일부터 시행.

### 무엇을 보고해야 하나
제조사는 자사 제품(디지털 요소가 포함된 제품)의 보안에 영향을 미치는 '실제 악용 중인 취약점'과 '심각한 보안 사고'를 신고해야 한다.

### 신고 기한 (3단계)
인지한 시점부터 24시간 내 조기경보(early warning)를 제출하고, 72시간 내 전체 통지(full notification)를 제출해야 한다. 최종 보고서는 실제 악용 취약점의 경우 시정조치가 마련된 후 14일 이내, 심각한 사고의 경우 1개월 이내에 제출해야 한다.

### 신고 대상 및 경로
제조사는 CRA 단일신고플랫폼(Single Reporting Platform, SRP)을 통해 한 번만 신고하면 된다. 통지는 주사업장이 위치한 회원국의 CSIRT(컴퓨터 보안사고 대응팀)로 전달되며, 예외적인 경우가 아니라면 동시에 ENISA에도 정보가 제공된다.

### 왜 중요한가 — 신제품만이 아니라 "레거시 제품"도 포함
이 보고 의무는 CRA가 전면 적용되기 전 EU 시장에 이미 출시된 모든 대상 제품에도 2026년 9월 11일부터 적용됩니다(Art. 69(3) CRA). 이는 곧, 신규 출시 제품뿐 아니라 과거에 출시한 레거시 제품도 CRA 신고 절차의 대상이 된다는 실질적 의미를 갖는다.

### 다른 의무와의 관계 (혼동 주의)
많은 기업이 "2027년까지 여유가 있다"고 오해하지만, CRA는 2024년 12월 10일 발효되어 원칙적으로 2027년 12월 11일부터 전면 적용되지만, Article 14에 따른 보고 의무는 그보다 1년 이상 앞선 2026년 9월 11일부터 적용됩니다(Art. 71(2) CRA). 다만, 취약점 패치·시정 등 다른 요건들은 2027년 12월 11일까지 시행되지 않습니다.

### 참고: 취약점 신고 = 공개 아님
신고를 한다고 해서 취약점이 즉시 공개되는 것은 아닙니다. 신고 내용은 신뢰할 수 있는 사이버보안 당국 네트워크 내에서 처리되며, 통상적으로 패치가 나올 때까지 공개 공표는 보류됩니다.

---

**실무 준비 사항** (신고 의무 시행 전 필요한 것들):
- CRA 대상 제품 인벤토리 구축(신제품+레거시 포함)
- 책임 법인 식별(그룹사, OEM 구조 등)
- SBOM(소프트웨어 구성요소 명세) 및 자동화된 취약점 추적 체계 마련
- SRP(단일신고플랫폼) 등록 및 담당 CSIRT 파악

참고로 2026년 6월 11일에는 적합성평가기관(Conformity Assessment Bodies) 통보 관련 조항이 시행되었고, 2026년 3분기에는 첫 표준화 결과물이 나올 예정이라 2026년은 CRA 이행의 여러 이정표가 몰려 있는 해입니다.
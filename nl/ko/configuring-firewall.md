---

copyright:
  years: 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 방화벽 구성

방화벽을 구성하는 작업은 다른 소스의 트래픽은 거부하는 반면 특정 인터넷 주소의 IP 주소/포트에 대한 액세스는 허용하도록 규칙 세트를 작성하는 것만큼 간단합니다.

## 서버에 방화벽 추가

서버에 방화벽을 추가하려면, 고객 포털에서 **디바이스 > 디바이스 목록 > 원하는 서버 클릭 > 구성 > 페이지 맨 아래: Hardware Firewall 주문** 링크를 클릭하십시오. 선택한 서버의 업링크 속도를 기반으로 적합한 방화벽에 대한 주문 프로세스가 시작됩니다. 오류가 발생하는 경우 [알려진 제한사항](known-limitations.html)을 참조하거나 SoftLayer 지원 팀에 문의하십시오.

## 규칙 편집

처음으로 방화벽을 서버에 추가하는 경우 모든 트래픽이 서버에 도달할 수 있도록 규칙 세트가 초기에 실시됩니다. 그리고 나면 서버에 도달하는 트래픽을 제어하기 위해 규칙을 편집할 수 있습니다.

"상태"가 방화벽이 "규칙을 모두 처리 중"임을 나타내는지 확인하십시오. 사용자는 구현된 규칙이 환경에 의도하지 않은 영향을 미치는 경우 **조치** 드롭 다운에서 **규칙 무시**를 클릭하여 규칙을 무시하도록 선택할 수 있습니다.

1. 브라우저에서 [고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){: new_window}을 열고 계정에 로그인하십시오.
2. 고객 포털 탐색에서 **디바이스 > 디바이스 목록**으로 이동하여 구성하려는 디바이스를 보호하는 방화벽을 클릭하십시오.
3. **방화벽** 탭에서 "상태"가 방화벽이 "규칙을 모두 처리 중"임을 나타내는지 확인하십시오.  페이지에 IPv4 및 IPv6 주소에 영향을 미치는 현재 규칙이 표시됩니다. 규칙이 구현되지 않은 경우 희미해진 플레이스홀더가 표시됩니다. 이 때 현재 규칙을 편집하는 데 링크를 사용할 수 있습니다.  이 규칙 목록이 '작업 중인 구성'으로 알려져 있습니다. '작업 중인 구성'은 작성 중이지만 아직 방화벽에 적용되지 않은 규칙 세트입니다. 사용자는 규칙 세트가 완료될 때까지 규칙을 편집, 추가 및 삭제할 수 있습니다. 

     규칙은 처리되는 순서대로 표시되며 번호가 낮은 규칙이 번호가 높은 규칙보다 우선권을 갖습니다(규칙 1이 패킷을 통과하도록 허용하면 규칙 2 이후는 패킷에서 무시함).
     
     필드는 다음과 같습니다.

      **주문** - 이 필드는 규칙 번호를 포함합니다.  제공된 화살표를 사용하여 규칙을 목록에서 위 또는 아래로 이동할 수 있습니다.
      
      **조치** - 이 선택 목록은 이 규칙과 일치하는 트래픽을 '허용' 또는 '거부'하는 데 사용됩니다.
      
      **소스** - 이 필드는 '임의', 특정 IP 주소 또는 특성 서브넷의 네트워크 주소 중 하나일 수 있습니다.
      
      **CIDR** - 이 필드는 선택한 소스에 대한 표준 CIDR 표기법을 나타냅니다. 예를 들어, "24"는 256개 IP에 대한 규칙을 구현하는 반면, "32"는 단일 IP에 대한 규칙을 구현합니다.
      
      **대상** - 이 필드는 대상 IP를 선택합니다(문제가 있는 경우 [알려진 제한사항](known-limitations.html) 참조).
      
      **CIDR** - 이 필드는 선택한 대상의 표준 CIDR 표기법을 나타냅니다.
      
      **포트 범위** - 이러한 두 개 필드는 규칙을 적용하는 포트의 범위를 나타냅니다(1 - 65535 사이).
      
      **프로토콜** - 이 필드는 규칙을 적용하는 프로토콜을 선택합니다(TCP/GRE/ICMP/UDP/PPTP/AH/ESP).
      
      **참고:** 이 규칙에 대한 참고사항을 입력하는 자유 양식 필드입니다.

4. 편집할 규칙을 클릭하거나 규칙을 추가하려면 테이블의 맨 아래 있는 더하기 기호를 클릭하십시오. 빼기 아이콘을 클릭하면 규칙이 삭제됩니다. 규칙을 입력하면 자동으로 유효성이 검증됩니다.
5. '작업 중인 구성'이 완료되면 **규칙 업데이트** 단추를 눌러서 방화벽에 '작업 중인 구성'을 적용하십시오. 규칙은 2분 안에 적용됩니다.

## 공통 포트

|프로토콜 |포트 |
| :-----: | :-----: |
|FTP |21 |
|SSH |22 |
|Telnet |23 |
|SMTP |25 |
|DNS |53 |
|HTTP |80 |
|POP3 |110 |
|IMAP |143 |
|HTTPS |443 |
|MSSQL |1433 |
|MySQL |3306 |
|원격 데스크탑 |3389 |
|PostgreSQL |5432 |
|VNC 웹 |5800 |
|VNC 클라이언트 |5900 |
|Urchin |9999 또는 10000 ||

    

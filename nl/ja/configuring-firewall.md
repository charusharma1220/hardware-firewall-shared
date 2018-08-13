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

# ファイアウォールの構成

ファイアウォールの構成手順は、一連のルールを作成して、特定のインターネット・アドレスから特定の IP アドレス/ポートへのアクセスを許容し、その他のソースからのトラフィックを拒否するという程度の単純なものです。

## サーバーへのファイアウォールの追加

サーバーにファイアウォールを追加するには、カスタマー・ポータルで、**「デバイス」>「デバイス・リスト」リンクをクリック > 目的のサーバーをクリック >「構成」をクリック > ページの下部で「ハードウェア・ファイアウォールの注文」をクリック**の順に操作を行います。 これにより、選択したサーバーのアップリンク速度に基づいて、適切なファイアウォールの注文プロセスが開始されます。 エラーを受け取った場合、[既知の制限](known-limitations.html)の参照、SoftLayer サポートへの問い合わせ、またはこの両方を行ってください。

## ルールの編集

サーバーにファイアウォールが初めて追加されると、サーバーに到達するすべてのトラフィックを許可する一連のルールが最初に実施されます。 その後、サーバーに到達するトラフィックを制御するために、ルールを編集できます。

「状況」で、ファイアウォールが「すべてのルールを処理」となっていることを確認します。 実施されているルールにより、ご使用の環境が望ましくない影響を受けた場合、ユーザーは**「アクション」**ドロップダウンで**「ルールのバイパス」**をクリックすることで、ルールのバイパスを選択できます。

1. ブラウザーから、[カスタマー・ポータル![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){: new_window}を開き、アカウントにログインします。
2. カスタマー・ポータル・ナビゲーションで、**「デバイス」>「デバイス・リスト」**に移動し、ファイアウォールで保護されているデバイスのうち、構成するものをクリックします。
3. **「ファイアウォール」**タブの「状況」で、ファイアウォールが「すべてのルールを処理」となっていることを確認します。  このページには、IPv4 アドレスおよび IPv6 アドレスに対して現在有効になっているルールが表示されます。 ルールが実施されていない場合、フェード状態のプレースホルダーが表示されます。 この時点で、現在のルールを編集するためのリンクを使用できます。  このルールのリストは「作業構成」と呼ばれます。 「作業構成」は、作成中であり、ファイアウォールにはまだ適用されていない一連のルールです。 ルールを編集、追加、削除して、ルール・セットを完成させます。 

     ルールは、処理される順番に表示されます。番号が小さいルールは、番号が大きいルールよりも優先されます (ルール 1 によりパケット通過が許可される場合、ルール 2 以降はそのパケットに適用されません)。
     
     フィールドを以下に示します。

      **順序 (Order)** - このフィールドには、ルール番号が含まれます。  表示されている矢印を使用して、ルールをリストの上または下に移動できます。
      
      **アクション** - この選択リストを使用して、このルールと一致するトラフィックを「許可」または「拒否」します。
      
      **ソース** - このフィールドには、「すべて (any)」、特定の IP アドレス、または特定のサブネットのネットワーク・アドレスを指定できます。
      
      **CIDR** - このフィールドは、選択したソースの標準 CIDR 表記を示します。 例えば、「32」では 1 つの IP に対してルールが実施され、一方「24」では 256 個の IP に対してルールが実施されます。
      
      **宛先** - このフィールドでは、宛先 IP を選択します (問題が発生した場合は、[既知の制限](known-limitations.html)を参照してください)。
      
      **CIDR** - このフィールドは、選択した宛先の標準 CIDR 表記を示します。
      
      **ポートの範囲** - これらの 2 つのフィールドは、ルールを適用するポートの範囲 (1 から 65535 の間) を示します。
      
      **プロトコル** - このフィールドでは、ルールを適用するプロトコル (TCP/GRE/ICMP/UDP/PPTP/AH/ESP) を選択します。
      
      **メモ** - このルールに関するメモを入力するためのフリー・フォーム・フィールド。

4. ルールをクリックすると、そのルールを編集できます。また、テーブルの下部にある正符号をクリックすると、ルールを追加できます。 負符号のアイコンをクリックすると、ルールが削除されます。 ルールは、入力すると、自動的に検証されます。
5. 「作業構成」が完了したら、**「ルールの更新」**ボタンを押して「作業構成」をファイアウォールに適用します。 ルールは 2 分以内に有効になります。

## 共通ポート

| プロトコル | ポート |
| :-----: | :-----: |
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |
| MSSQL | 1433 |
| MySQL | 3306 |
| リモート・デスクトップ | 3389 |
| PostgreSQL | 5432 |
| VNC Web | 5800 |
| VNC クライアント | 5900 |
| Urchin | 9999 または 10000 ||

    
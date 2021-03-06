---
title: Windows PC 用ファイアウォール ポリシー
titleSuffix: Microsoft Intune
description: Intune を使用すると、Intune クライアントで管理する PC をさまざまな方法で保護することができます。たとえば、Windows ファイアウォールの設定を構成できます。
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2c736c905045fd3afd40a12243986fbe69452ecd
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502833"
---
# <a name="help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune"></a>Microsoft Intune で Windows ファイアウォール ポリシーを使用して Windows PC を保護する

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

> [!NOTE]
> このトピックの情報は、Intune ソフトウェア クライアントを使用して PC として管理している Windows デスクトップにのみ適用されます。 モバイルデバイスとして登録されている Windows Pc のファイアウォール設定を管理する場合は、「 [Intune での endpoint protection 設定の追加](../protect/endpoint-protection-configure.md)」を参照してください。

Microsoft Intune を使用すると、Intune クライアントで管理する Windows PC をさまざまな方法で保護することができます。 たとえば、PC で Windows ファイアウォールの設定を構成できるようにするポリシーを提供できます。

まだ Intune Windows PC クライアントをコンピューターにインストールしていない場合は、「[Microsoft Intune を使用して Windows PC クライアントをインストールする](install-the-windows-pc-client-with-microsoft-intune.md)」を参照してください。

Windows PC で Windows ファイアウォール ポリシーを構成、展開、監視する方法については、以下のセクションの情報を参照してください。

## <a name="use-intune-policies-to-manage-windows-firewall"></a>Intune ポリシーを使用して Windows ファイアウォールを管理する
Windows ファイアウォール ポリシーを使用すると、管理された PC の Windows ファイアウォールを制御する設定を作成し、展開することができます。 Windows ファイアウォールのカスタム例外を管理することはできません。また、これらの設定はサードパーティ製ファイアウォールには影響しません。

> [!NOTE]
> Microsoft Intune ポリシーとグループ ポリシーが同じ PC 上で同じ設定を管理するように構成されている場合、グループ ポリシー設定が Microsoft Intune ポリシー設定をオーバーライドします。 Intune ポリシーとグループ ポリシー間の競合を解決する方法については、「[GPO と Microsoft Intune ポリシーの競合を解決する](resolve-gpo-and-microsoft-intune-policy-conflicts.md)」をご覧ください。
>
> Windows Vista 搭載コンピューターに Windows ファイアウォールの設定を展開する場合は、最初に[修正プログラム KB971800](https://support2.microsoft.com/kb/971800) をこれらのコンピューターにインストールする必要があります。

> [!IMPORTANT]
> Intune を使用して Windows ファイアウォールを管理するには、管理対象のコンピューターで次の 2 つのサービスを有効にする必要があります。
>
> - Windows ファイアウォール
> - IPSec ポリシー エージェント

## <a name="configure-a-windows-firewall-policy"></a>Windows ファイアウォール ポリシーの構成

1. [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、 **[ポリシー]** &gt; **[ポリシーの追加]** を選択します。

2. **Windows ファイアウォール設定** ポリシーを構成し、展開します。 推奨される設定を使用することも、設定をカスタマイズすることもできます。 ポリシーの作成および展開方法の詳細については、「[Microsoft Intune コンピューター クライアントを使用した一般的な Windows PC 管理タスク](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)」を参照してください。

    次のセクションでは、ポリシーに構成できる値と、ポリシーをカスタマイズしない場合に使用される既定値を示します。

Windows ファイアウォール ポリシーを展開したら、 **[ポリシー]** ワークスペースの **[すべてのポリシー]** ページでその状態を確認できます。

## <a name="specify-policy-settings-for-windows-firewall"></a>Windows ファイアウォールのポリシー設定を指定する

### <a name="turn-on-windows-firewall"></a>Windows ファイアウォールを有効にする

これらのポリシー設定は、次のようなマネージド コンピューターで Windows ファイアウォールを有効にします。
- ドメインに接続されている (職場など)
- プライベート (信頼された) ネットワークに接続されている (ホーム ネットワークなど)
- 信頼されていないパブリック ネットワークに接続されている (喫茶店など)

これらの各設定の既定値は、最も安全な値である **[はい]** です。



### <a name="block-all-incoming-connections-including-those-in-the-list-of-allowed-programs"></a>許可されたプログラムの一覧にあるプログラムからの接続も含み、すべての着信をブロックする

これらのポリシー設定は、次のようなマネージド コンピューターで着信ネットワーク トラフィックをブロックするように Windows ファイアウォールを構成します。
- ドメインに接続されている (職場など)
- プライベート (信頼された) ネットワークに接続されている (ホーム ネットワークなど)
- 信頼されていないパブリック ネットワークに接続されている (喫茶店など)

これらの各設定の既定値は、最も安全な値である **[はい]** です。

> [!IMPORTANT]
> マネージド コンピューターの中に、サービスパックなしの Windows Vista を実行しているものがある場合は、Microsoft サポート技術情報の[記事 971800](https://go.microsoft.com/fwlink/?LinkId=188405) にある更新プログラムをダウンロードしてインストールするか、これらのコンピューターに展開するポリシーの **[すべてのプログラムからの接続をブロックする]** 設定を無効にする必要があります。

### <a name="notify-the-user-when-windows-firewall-blocks-a-new-program"></a>Windows ファイアウォールが新しいプログラムをブロックしたときにユーザーに通知する

これらのポリシー設定は、次のようなマネージド コンピューターで着信ネットワーク トラフィックをブロックしたときに Windows ファイアウォールが PC ユーザーに通知するかどうかを決定します。
- ドメインに接続されている (職場など)
- プライベート (信頼された) ネットワークに接続されている (ホーム ネットワークなど)
- 信頼されていないパブリック ネットワークに接続されている (喫茶店など)

これらの各設定の既定値は **[はい]** です。


### <a name="configure-predefined-exceptions"></a>定義済みの例外を構成する

前に構成した値に関係なく特定の種類のネットワーク トラフィックがファイアウォールを通過するのを許可する例外を構成することができます。 既定では、いずれの設定も構成されません。

|設定の名前|説明|
|------------------|--------------------|
|**BranchCache - コンテンツの取得**<br>(Windows 7 以降)|BranchCache クライアントが HTTP を使用して、分散モードの他の BranchCache から、およびホスト型キャッシュ モードのホスト型キャッシュから、コンテンツを取得できるようにします。 この設定は HTTP を使用します。|
|**BranchCache - ホスト型キャッシュ クライアント**<br>(Windows 7 以降)|BranchCache クライアントでホスト型キャッシュを使用できるようになります。 この設定は HTTPS を使用します。|
|**BranchCache - ホスト型キャッシュ サーバー**|BranchCache クライアントでホスト型キャッシュを使用して、他のクライアントと通信できるようになります。 この設定は HTTPS を使用します。|
|**BranchCache - ピア検出**<br>(Windows 7 以降)|BranchCache クライアントで Web Services Dynamic Discovery (WS-Discovery) プロトコルを使用して、ローカル サブネット上のコンテンツの可用性を調べられるようになります。|
|**BITS ピア キャッシュ**|クライアントでバックグラウンド インテリジェント転送サービス (BITS) を使用して、同じサブネット内にあるクライアントの BITS キャッシュに保存されているファイルを検索して共有できるようになります。 この設定は、Web Services on Devices (WSDAPI) およびリモート プロシージャ コール (RPC) を使用します。|
|**ネットワーク プロジェクターへの接続**|ユーザーは、有線ネットワークまたはワイヤレス ネットワーク経由でプロジェクターに接続し、プレゼンテーションを投影できるようになります。 この設定は WSDAPI を使用します。|
|**コア ネットワーク**|クライアントで IPv4 および IPv6 を使用して、ネットワーク リソースに接続できるようになります。|
|**分散トランザクション コーディネーター**|マネージド コンピューターで、データベース、メッセージ キュー、ファイル システムなどのトランザクションで保護されたリソースを更新するトランザクションをコーディネートできるようにします。|
|**ファイルとプリンターの共有**|ユーザーはローカル ファイルとプリンターをネットワーク上の他のユーザーと共有できるようになります。 この設定は、NetBIOS、リンク ローカル マルチキャスト名前解決 (LLMNR)、サーバー メッセージ ブロック (SMB) プロトコル、および RPC を使用します。|
|**ホームグループ**<br>(Windows 7 以降)|マネージド コンピューターはホームグループ ネットワークに参加できるようになります。|
|**iSCSI サービス**|マネージド コンピューターは iSCSI サーバーとデバイスに接続できるようになります。|
|**キー管理サービス**|エンタープライズ環境内のコンピューターがライセンスの確認でカウントされるようになります。|
|**Media Center Extenders**|Windows Media Center を実行するコンピューターと Media Center Extenders が通信できるようになります。 この設定は、Simple Service Discovery Protocol (SSDP) および qWave を使用します。|
|**Netlogon サービス**|ドメイン クライアントとドメイン コントローラー間でのユーザー認証およびサービス認証のセキュリティ チャネルが構成されます。 この設定は RPC を使用します。|
|**ネットワーク探索**|コンピューターが他のデバイスを検出できるようになり、ネットワーク上の他のデバイスから検出されるようになります。 この設定は、機能探索ホストと発行サービス、SSDP、NetBIOS、LLMNR、および UPnP・ネットワーク プロトコルを使用します。|
|**パフォーマンス ログと警告**|パフォーマンス ログと警告サービスをリモート管理できるようになります。 この設定は RPC を使用します。|
|**リモート管理**|コンピューターをリモート管理できるようになります。|
|**リモート アシスタンス**|マネージド コンピューターのユーザーが、ネットワーク上の他のユーザーにリモート アシスタンスを依頼できるようになります。 この設定は、SSDP、ピア名解決プロトコル (PNRP)、Teredo、および UPnP ネットワーク プロトコルを使用します。|
|**リモート デスクトップ**|コンピューターでリモート デスクトップを使用して、他のコンピューターにアクセスできるようになります。|
|**リモート イベントのログ管理**|クライアント イベント ログをリモート環境から表示および管理できるようになります。 この設定は、名前付きパイプおよび RPC を使用します。|
|**スケジュールされたリモート タスク管理**|タスク スケジュール サービスをリモート管理できるようになります。 この設定は RPC を使用します。|
|**リモート サービス管理**|クライアントのローカル サービスをリモート管理できるようになります。 この設定は、名前付きパイプおよび RPC を使用します。|
|**リモート ボリューム管理**|ソフトウェアとハードウェア ディスク ボリュームをリモート管理できるようになります。 この設定は RPC を使用します。|
|**ルーティングとリモート アクセス**|コンピューターに対する受信 VPN とリモート アクセス接続が許可されます。|
|**Secure Socket トンネリング プロトコル**|Secure Socket トンネリング プロトコル (SSTP) を使用したマネージド コンピューターに対する受信 VPN 接続が許可されます。 この設定は HTTPS を使用します。|
|**SNMP トラップ**|マネージド コンピューターが簡易ネットワーク管理プロトコル (SNMP) トラップ サービス トラフィックを受信できるようになります。|
|**UPnP フレームワーク**|UPnP 証明済みデバイスを検出および使用できるように、コンピューターに UPnP フレームワーク サービスが構成されます。|
|**Windows グループ作業ツール コンピューター名の登録サービス**|コンピューターで SSDP と PNRP を使用して、他のコンピューターを検索し、通信できるようになります。|
|**Windows Media Player**|ユーザーはユーザー データグラム プロトコル (UDP) 経由でストリーミング メディアを受信できるようになります。|
|**Windows Media Player ネットワーク共有サービス**|ユーザーはネットワーク経由でメディアを共有できるようになります。 この設定は、SSDP、qWave、および UPnP ネットワーク プロトコルを使用します。|
|**Windows Media Player ネットワーク共有サービス (インターネット)**<br>(Windows 7 以降)|ユーザーはインターネット経由でホーム メディアを共有できるようになります。|
|**Windows ミーティング スペース**|ユーザーはネットワークを経由でドキュメント、プログラム、およびデスクトップを他のユーザーと共有して共同作業できるようになります。 この設定は、分散ファイル システム レプリケーション (DFSR) と P2P を使用します。|
|**Windows ピア ツー ピア共同作業ファンデーション**|さまざまなピア ツー ピア プログラムやテクノロジが接続できるように構成します。 この設定は SSDP と PNRP を使用します。|
|**Windows リモート管理 (互換)**|オペレーティング システムとデバイスのリモート管理用の Web サービス ベースのプロトコルである WS-Management を使用して、マネージド コンピューターをリモート管理できるようになります。|
|**Windows リモート管理**<br>(Windows 8 以降)|オペレーティング システムとデバイスのリモート管理用の Web サービス ベースのプロトコルである WS-Management を使用して、マネージド コンピューターをリモート管理できるようになります。|
|**Windows Virtual PC**<br>(Windows 7 以降)|仮想マシンが他のコンピューターと通信できるようになります。|
|**ワイヤレス ポータブル デバイス**|メディア転送プロトコル (MTP) を使用して、ネットワーク対応のカメラまたはメディア デバイスから、マネージド コンピューターにメディアを転送できるようになります。 この設定は、SSDP および UPnP ネットワーク プロトコルを使用します。|

## <a name="see-also"></a>関連項目
[Windows PC を保護するためのポリシー](policies-to-protect-windows-pcs-in-microsoft-intune.md)

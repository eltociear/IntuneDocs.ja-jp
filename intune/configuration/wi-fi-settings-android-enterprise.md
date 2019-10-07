---
title: Android エンタープライズ デバイスおよびキオスク デバイス用の Wi-Fi 設定 - Microsoft Intune | Microsoft Docs
description: Android エンタープライズ デバイスおよびキオスク デバイス用の Wi-Fi デバイス構成プロファイルを作成または追加します。 Microsoft Intune での証明書の追加、EAP の種類の選択、認証方式の選択など、他の設定もご覧ください。 キオスク デバイスの場合、ネットワークの事前共有キーも入力します。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 51096b4ff42902b5feb8cecdebf9d839821e1bb2
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733986"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Microsoft Intune で Android エンタープライズおよび Android キオスクを実行するデバイス用の Wi-Fi 設定を追加する

特定の Wi-Fi 設定でプロファイルを作成してから、Android エンタープライズ デバイスおよび Android 専用デバイスにこのプロファイルを展開することができます。 Microsoft Intune では、ネットワークに対する認証や、事前共有キーの使用など、多くの機能が提供されています。

この記事では、これらの設定について説明します。 [デバイス上で Wi-Fi を使用する](wi-fi-settings-configure.md)方法に関するページでは、Microsoft Intune の Wi-Fi 機能についてさらに詳しく説明されています。

## <a name="before-you-begin"></a>始める前に

[デバイス プロファイルを作成します](wi-fi-settings-configure.md#create-a-device-profile)。

## <a name="device-owner-only"></a>デバイスの所有者のみ

Android エンタープライズ専用デバイスをキオスクとして使用する場合は、このオプションを選択します。

### <a name="basic"></a>基本

- **[Wi-Fi の種類]** : **[Basic]** を選択します。
- **[ネットワーク名]** : この Wi-Fi 接続の名前を入力します。 エンド ユーザーがデバイスで利用可能な Wi-FI 接続を参照するときに、この名前が表示されます。 たとえば、「**Contoso WiFi**」と入力します。
- **[SSID]** :**サービスセット識別子**を入力します。これは、デバイスが接続するワイヤレスネットワークの実際の名前です。 ただし、ユーザーが接続を選択したときにユーザーに表示されるのは、構成された**ネットワーク名**のみです。
- **[自動的に接続する]** : **[有効]** を選択すると、デバイスが範囲内に入るとこのネットワークに自動的に接続します。 **[無効]** を選択すると、デバイスは自動的に接続されません。
- **[非公開のネットワーク]** : **[有効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれなくなります。 SSID はブロードキャストされません。 **[無効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれるようになります。
- **[Wi-Fi の種類]** : Wi-Fi ネットワークへの認証に使用するセキュリティ プロトコルを選択します。 次のようなオプションがあります。

  - **[オープン (認証なし)]** : このオプションは、ネットワークがセキュリティで保護されていない場合にのみ使用します。
  - **[WEP 事前共有キー]** : **[事前共有キー]** にパスワードを入力します。 組織のネットワークがセットアップまたは構成されるときに、パスワードまたはネットワーク キーも構成されます。 PSK の値に対して、このパスワードまたはネットワーク キーを入力します。
  - **[WPA 事前共有キー]** : **[事前共有キー]** にパスワードを入力します。 組織のネットワークがセットアップまたは構成されるときに、パスワードまたはネットワーク キーも構成されます。 PSK の値に対して、このパスワードまたはネットワーク キーを入力します。

### <a name="enterprise"></a>Enterprise

- **[Wi-Fi の種類]** : **[Enterprise]** を選択します。
- **[SSID]** :**サービスセット識別子**を入力します。これは、デバイスが接続するワイヤレスネットワークの実際の名前です。 ただし、ユーザーが接続を選択したときにユーザーに表示されるのは、構成された**ネットワーク名**のみです。
- **[自動的に接続する]** : **[有効]** を選択すると、デバイスが範囲内に入るとこのネットワークに自動的に接続します。 **[無効]** を選択すると、デバイスは自動的に接続されません。
- **[非公開のネットワーク]** : **[有効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれなくなります。 SSID はブロードキャストされません。 **[無効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれるようになります。
- **[EAP の種類]** : 次の中から、セキュリティで保護されたワイヤレス接続の認証に使用される拡張認証プロトコル (EAP) の種類を選択します。 次のようなオプションがあります。

  - **[EAP-TLS]** : 以下も入力します。

    - **[サーバー信頼]**  -  **[サーバー検証のためのルート証明書]** : 既存の信頼されたルート証明書プロファイルを選択します。 クライアントがネットワークに接続すると、この証明書がサーバーに対して提示され、接続が認証されます。

    - **[クライアント認証]**  -  **[クライアント認証に使用するクライアント証明書 (ID 証明書)]** : やはりデバイスに展開される SCEP または PKCS クライアント証明書プロファイルを選択します。 この証明書は、接続の認証のためにデバイスによってサーバーに提示される ID です。

    - **[ID プライバシー (外部 ID)]** : EAP ID 要求への応答で送信されるテキストを入力します。 このテキストには任意の値を指定できます (例: `anonymous`)。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。

  - **[EAP-TTLS]** : 以下も入力します。

    - **[サーバー信頼]**  -  **[サーバー検証のためのルート証明書]** : 既存の信頼されたルート証明書プロファイルを選択します。 クライアントがネットワークに接続すると、この証明書がサーバーに対して提示され、接続が認証されます。

    - **[クライアント認証]** : **[認証方法]** を選択します。 次のようなオプションがあります。

      - **[ユーザー名とパスワード]** : 接続の認証のためにユーザーにユーザー名とパスワードを要求します。 次の項目も入力します。
        - **[EAP 以外の方法 (内部 ID)]** : 接続を認証する方法を選択します。 Wi-Fi ネットワークで構成されているものと同じプロトコルを選択する必要があります。 次のようなオプションがあります。

          - **暗号化されていないパスワード (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP バージョン 2 (MS-CHAP v2)**

      - **[証明書]** : やはりデバイスに展開される SCEP または PKCS クライアント証明書プロファイルを選択します。 この証明書は、接続の認証のためにデバイスによってサーバーに提示される ID です。

      - **[ID プライバシー (外部 ID)]** : EAP ID 要求への応答で送信されるテキストを入力します。 このテキストには任意の値を指定できます (例: `anonymous`)。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。

  - **[PEAP]** : 次の項目も入力します。

    - **[サーバー信頼]**  -  **[サーバー検証のためのルート証明書]** : 既存の信頼されたルート証明書プロファイルを選択します。 クライアントがネットワークに接続すると、この証明書がサーバーに対して提示され、接続が認証されます。

    - **[クライアント認証]** : **[認証方法]** を選択します。 次のようなオプションがあります。

      - **[ユーザー名とパスワード]** : 接続の認証のためにユーザーにユーザー名とパスワードを要求します。 次の項目も入力します。
        - **[認証用の非 EAP メソッド (内部 ID)]** : 接続を認証する方法を選択します。 Wi-Fi ネットワークで構成されているものと同じプロトコルを選択する必要があります。 次のようなオプションがあります。

          - **なし**
          - **Microsoft CHAP バージョン 2 (MS-CHAP v2)**

      - **[証明書]** : やはりデバイスに展開される SCEP または PKCS クライアント証明書プロファイルを選択します。 この証明書は、接続の認証のためにデバイスによってサーバーに提示される ID です。

      - **[ID プライバシー (外部 ID)]** : EAP ID 要求への応答で送信されるテキストを入力します。 このテキストには任意の値を指定できます (例: `anonymous`)。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。

## <a name="work-profile-only"></a>仕事用プロファイルのみ

### <a name="basic"></a>基本

- **[Wi-Fi の種類]** : **[Basic]** を選択します。
- **[SSID]** :**サービスセット識別子**を入力します。これは、デバイスが接続するワイヤレスネットワークの実際の名前です。 ただし、ユーザーが接続を選択したときにユーザーに表示されるのは、構成された**ネットワーク名**のみです。
- **[自動的に接続する]** : **[有効]** を選択すると、デバイスが範囲内に入るとこのネットワークに自動的に接続します。 **[無効]** を選択すると、デバイスは自動的に接続されません。
- **[非公開のネットワーク]** : **[有効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれなくなります。 SSID はブロードキャストされません。 **[無効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれるようになります。

### <a name="enterprise"></a>Enterprise

- **[Wi-Fi の種類]** : **[Enterprise]** を選択します。
- **[SSID]** :**サービスセット識別子**を入力します。これは、デバイスが接続するワイヤレスネットワークの実際の名前です。 ただし、ユーザーが接続を選択したときにユーザーに表示されるのは、構成された**ネットワーク名**のみです。
- **[自動的に接続する]** : **[有効]** を選択すると、デバイスが範囲内に入るとこのネットワークに自動的に接続します。 **[無効]** を選択すると、デバイスは自動的に接続されません。
- **[非公開のネットワーク]** : **[有効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれなくなります。 SSID はブロードキャストされません。 **[無効]** を選択すると、デバイスで使用可能なネットワークのリストにこのネットワークが含まれるようになります。
- **[EAP の種類]** : 次の中から、セキュリティで保護されたワイヤレス接続の認証に使用される拡張認証プロトコル (EAP) の種類を選択します。 次のようなオプションがあります。

  - **[EAP-TLS]** : 以下も入力します。

    - **[サーバー信頼]**  -  **[サーバー検証のためのルート証明書]** : 既存の信頼されたルート証明書プロファイルを選択します。 クライアントがネットワークに接続すると、この証明書がサーバーに対して提示され、接続が認証されます。

    - **[クライアント認証]**  -  **[クライアント認証に使用するクライアント証明書 (ID 証明書)]** : やはりデバイスに展開される SCEP または PKCS クライアント証明書プロファイルを選択します。 この証明書は、接続の認証のためにデバイスによってサーバーに提示される ID です。

    - **[ID プライバシー (外部 ID)]** : EAP ID 要求への応答で送信されるテキストを入力します。 このテキストには任意の値を指定できます (例: `anonymous`)。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。

  - **[EAP-TTLS]** : 以下も入力します。

    - **[サーバー信頼]**  -  **[サーバー検証のためのルート証明書]** : 既存の信頼されたルート証明書プロファイルを選択します。 クライアントがネットワークに接続すると、この証明書がサーバーに対して提示され、接続が認証されます。

    - **[クライアント認証]** : **[認証方法]** を選択します。 次のようなオプションがあります。

      - **[ユーザー名とパスワード]** : 接続の認証のためにユーザーにユーザー名とパスワードを要求します。 次の項目も入力します。
        - **[EAP 以外の方法 (内部 ID)]** : 接続を認証する方法を選択します。 Wi-Fi ネットワークで構成されているものと同じプロトコルを選択する必要があります。 次のようなオプションがあります。

          - **暗号化されていないパスワード (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP バージョン 2 (MS-CHAP v2)**

      - **[証明書]** : やはりデバイスに展開される SCEP または PKCS クライアント証明書プロファイルを選択します。 この証明書は、接続の認証のためにデバイスによってサーバーに提示される ID です。

      - **[ID プライバシー (外部 ID)]** : EAP ID 要求への応答で送信されるテキストを入力します。 このテキストには任意の値を指定できます (例: `anonymous`)。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。

  - **[PEAP]** : 次の項目も入力します。

    - **[サーバー信頼]**  -  **[サーバー検証のためのルート証明書]** : 既存の信頼されたルート証明書プロファイルを選択します。 クライアントがネットワークに接続すると、この証明書がサーバーに対して提示され、接続が認証されます。

    - **[クライアント認証]** : **[認証方法]** を選択します。 次のようなオプションがあります。

      - **[ユーザー名とパスワード]** : 接続の認証のためにユーザーにユーザー名とパスワードを要求します。 次の項目も入力します。
        - **[認証用の非 EAP メソッド (内部 ID)]** : 接続を認証する方法を選択します。 Wi-Fi ネットワークで構成されているものと同じプロトコルを選択する必要があります。 次のようなオプションがあります。

          - **なし**
          - **Microsoft CHAP バージョン 2 (MS-CHAP v2)**

      - **[証明書]** : やはりデバイスに展開される SCEP または PKCS クライアント証明書プロファイルを選択します。 この証明書は、接続の認証のためにデバイスによってサーバーに提示される ID です。

      - **[ID プライバシー (外部 ID)]** : EAP ID 要求への応答で送信されるテキストを入力します。 このテキストには任意の値を指定できます (例: `anonymous`)。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。

## <a name="next-steps"></a>次の手順

プロファイルは作成されますが、何も実行されません。 次に、[プロファイルを割り当て](device-profile-assign.md)、[その状態を監視](device-profile-monitor.md)します。

[Android](wi-fi-settings-android.md)、[iOS](wi-fi-settings-ios.md)、[macOS](wi-fi-settings-macos.md)、[Windows 10](wi-fi-settings-windows.md)、および [Windows 8.1](wi-fi-settings-import-windows-8-1.md) デバイスの Wi-Fi プロファイルも作成できます。
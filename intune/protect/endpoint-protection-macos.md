---
title: Microsoft Intune - Azure で macOS のエンドポイント保護を追加する | Microsoft Docs
description: macOS デバイスで、ゲートキーパーを利用し、Mac App Store など、アプリをインストールできる場所を決定します。 他にも、ファイアウォールを有効にして (あるいは構成して) 特定のアプリを許可または禁止したり、ステルス モードを利用したり、さらには Microsoft Intune を利用し、特定の種類の着信接続をブロックしたりします。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6090d329eee6f27da21b6133a2b7ccdc7072feb3
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814109"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Intune での MacOS エンドポイント保護設定  

この記事では、macOS を稼働しているデバイスに対して構成できるすべてのエンドポイント保護設定について説明します。 これらの設定を構成するには、Intune の[endpoint protection](endpoint-protection-configure.md)の macOS デバイス構成プロファイルを使用します。  

## <a name="gatekeeper"></a>ゲートキーパー  

- **これらの場所からダウンロードされたアプリを許可する**  
  アプリのダウンロード元の場所に応じて、デバイスが起動できるアプリを制限します。 その目的は、マルウェアからデバイスを保護し、信頼しているソースからのアプリだけを許可することです。  

  - **未構成**  
  - **Mac App Store**  
  - **[Mac App Store and identified developers]\(Mac App Store と確認済みの開発者\)**  
  - **[どこでも]**  

  **既定値**: 未構成  

- **ユーザーはゲートキーパーを上書きできます**  
  ユーザーがゲートキーパー設定をオーバーライドすることを禁止し、Control キーを押しながらクリックしてアプリをインストールすることを防止します。 有効にすると、ユーザーはあらゆるアプリを Control キーを押しながらクリックし、インストールできます。  
 
  - **未構成**-ユーザーがコントロールをクリックして、アプリをインストールできます。  
  - **ブロック**-ユーザーがコントロールを使用してアプリをインストールできないようにします。  

  **既定値**: 未構成  

## <a name="firewall"></a>ファイアウォール  

ファイアウォールを利用し、ポート別ではなく、アプリケーション別に接続を制御します。 アプリケーション別の設定を利用することで、ファイアウォール保護の長所を簡単に引き出すことができます。 また、正しいアプリのために開いているネットワーク ポートが望ましくないアプリに支配されるのを防ぎます。  

**全般**
- **ファイアウォール**  
  ファイアウォールを有効にして、使用する環境における着信接続の処理方法を構成します。  
  - **未構成**  
  - **有効化**  

  **既定値**: 未構成  

- **着信接続**  
  DHCP、Bonjour、IPSec など、基本的なインターネット サービスに必要な接続を除き、すべての着信接続をブロックします。 この機能によって、ファイル共有や画面共有など、あらゆるすべての共有サービスもブロックされます。 共有サービスを利用している場合、この設定を *[未構成]* にしてください。  
  - **未構成**  
  - **ブロック**  

  **既定値**: 未構成  

**特定のアプリの着信接続を許可またはブロックします。**  

  - **許可されるアプリ**  
    着信接続を受け入れることが明示的に許可されているアプリを選択します。  

  - **ブロックされたアプリ**  
    着信接続をブロックする必要があるアプリを選択します。  

  - **ステルス モード**  
    コンピューターがプローブ要求に応答するのを防ぐには、ステルス モードを有効にします。 デバイスは引き続き、許可されているアプリに関する着信要求に応答します。 ICMP (ping) などの予期しない要求は無視されます。  
    - **未構成**  
    - **有効化**  

    **既定値**: 未構成  

## <a name="filevault"></a>FileVault  
Apple FileVault の設定の詳細については、Apple developer コンテンツの[FDEFileVault](https://developer.apple.com/documentation/devicemanagement/fdefilevault)を参照してください。 

> [!IMPORTANT]  
> MacOS 10.15 の場合、FileVault 構成では、ユーザーが承認した MDM 登録が必要です。 

- **FileVault**  
  MacOS 10.13 以降を実行するデバイスでは、XTS-AES-AES 128 と FileVault を使用して、フルディスク暗号化を*有効に*することができます。  
  - **未構成**  
  - **有効化**  

  **既定値**: 未構成  

  - **回復キーの種類**  
    デバイス用に、*個人キー*の回復キーが作成されます。 個人用キーに関する次の設定を構成します。  

    - **[個人用回復キーの場所]** -個人用回復キーを取得する方法と場所を説明する短いメッセージをユーザーに指定します。 このテキストは、パスワードを忘れた場合に個人回復キーを入力するように求められたときに、ユーザーがログイン画面に表示されるメッセージに挿入されます。  
      
    - **個人用回復キーのローテーション**-デバイスの個人回復キーを交換する頻度を指定します。 **[未構成]** の既定値を選択することも、 **1** ~ **12**か月の値を選択することもできます。  

  - **サインアウト時のプロンプトを無効にする**  
    ユーザーがサインアウトしたときに FileVault を有効にするように要求するプロンプトを表示しないようにします。[無効] に設定すると、サインアウト時のプロンプトが無効になり、ユーザーはサインインするときにメッセージが表示されます。  
    - **未構成**  
    - **無効**-サインアウト時にプロンプトを無効にします。

    **既定値**: 未構成  

  - **バイパスが許可される回数**  
  ユーザーがサインインするために FileVault が必要になる前に、ユーザーが FileVault を有効にするためのプロンプトを無視できる回数を設定します。 

    - 構成されて**いない**-次のサインインが許可される前に、デバイスの暗号化が必要です。  
    - **1** ~ **10** -デバイスで暗号化を要求する前に、ユーザーが 1 ~ 10 回のプロンプトを無視できるようにします。  
    - **制限はありません。常にプロンプト**が表示されます。ユーザーは FileVault を有効にするように求められますが、暗号化は必要ありません。  
 
    **既定値**:*変化*-[*サインアウト時にプロンプト*を表示しない] 設定が **[未構成]** に設定されている場合、この設定は既定で **[未構成]** に設定されます。 [*サインアウト時にプロンプト*を表示しない] が**無効**に設定されている場合、この設定の既定値は**1**であり、[未構成] の値はオプションでは**ありませ**ん。

Intune での FileVault の詳細については、「 [FileVault recovery keys](encryption-monitor.md#filevault-recovery-keys)」を参照してください。

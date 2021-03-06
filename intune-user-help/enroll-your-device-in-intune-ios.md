---
title: iOS デバイスからの会社のリソースへのアクセスを設定する | Microsoft Docs
description: iOS デバイスを Intune で管理する方法について説明します
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: bd9fd38fdc244bc48333496c2f266ff039e55585
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75855565"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>iOS デバイスからの会社のリソースへのアクセスを設定する  

組織の電子メール、ファイル、およびアプリに安全にアクセスするために、Intune ポータル サイト アプリで iOS デバイスを登録します。

デバイスが登録されると、*マネージド*になります。 組織は、Intune などのモバイル デバイス管理 (MDM) プロバイダーを介してデバイスにポリシーとアプリを割り当てることができます。  

> [!NOTE]
> Microsoft では、いかなる理由でも、Microsoft のサービスによって収集されたデータを第三者に販売することはありません。  

デバイスから職場または学校の情報へのアクセスを維持するには、組織の推奨される設定と一致するようにデバイスを構成する必要があります。 この記事では、ポータル サイトを使用してデバイスを登録し、組織の設定要件を維持する方法について説明します。  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> メール アプリで会社のメールにアクセスしようとしたときに、デバイスを管理対象にすることを求めるメッセージが表示された場合は問題ありません。 iOS デバイスから電子メールやその他の会社リソースにアクセスするには、以下の手順に従います。  


## <a name="what-to-expect-from-the-company-portal-app"></a>ポータル サイト アプリでできること  

### <a name="security"></a>セキュリティ  
初期セットアップ時に、アプリで自分自身を組織に対して認証する必要があります。 その後、更新する必要があるデバイス設定が通知されます。 たとえば、組織では多くの場合、満たす必要のあるパスワードの最小または最大文字数に関する要件が設定されます。

### <a name="protection"></a>保護  
デバイスが登録された後、ポータル サイト アプリでは引き続きデバイスが保護されていることが確認されます。 たとえば、信頼できないソースからアプリをインストールする場合、アプリにアラートが示され、会社のデータへのアクセスが取り消されることがあります。 この種類のポリシーは組織では一般的なものであり、再度アクセスできるようになるには、多くの場合、信頼できないアプリをアンインストールする必要があります。  

### <a name="setting-notifications"></a>通知の設定  
登録後、組織で多要素認証などの新しいセキュリティ要件が適用された場合、ポータル サイト アプリによって通知されます。 デバイスから作業を続行できるように、設定を調整することができます。  

登録の詳細については、[ポータル サイト アプリをインストールして、デバイスを登録するとどうなるか](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios)についてのページを参照してください。  

## <a name="enroll-your-ios-device"></a>iOS デバイスを登録する  

App Store に移動して、[Intune ポータル サイト アプリ](install-and-sign-in-to-the-intune-company-portal-app-ios.md)をダウンロードしてデバイスにインストールします。 また、登録中は、Wi-Fi 接続を維持し、Safari にアクセスできる必要があります。 

登録時に数分以上一時停止すると、アプリが閉じたりセットアップが終了したりする場合があります。 これが発生した場合は、ポータル サイト アプリを開いてもう一度やり直してください。  

1. ポータル サイトを開き、職場または学校アカウントでサインインします。  

2. ポータル サイトの通知を受け取るように求められたら、 **[許可]** をタップします。 ポータル サイトでは、たとえばデバイスの設定を更新する必要がある場合に、通知を使用してアラートを表示します。  

3. **[Set up access]\(アクセス設定\)** 画面で、 **[開始]** を選択します。   

    ![ポータル サイトの [アクセス設定] 画面のスクリーンショット例](./media/ios-enrollment-checklist-1909.PNG)  

4. **[デバイスと登録の種類の選択**] 画面が表示され、デバイスの種類を入力するように求められます。  
    * 組織からデバイスを受け取った場合は、タップ **(組織) がこのデバイスを所有**します。 次に、この記事の「[デバイス全体をセキュリティで保護](###secure-entire-device)する」に進み、セットアップを完了します。  
    * 自宅から持ち込む個人のデバイスを使用している場合は、**このデバイスを所有**しています。 次の手順に進みます。  

    この画面が表示されない場合は、「[デバイス全体をセキュリティで保護](enroll-your-device-in-intune-ios.md#secure-entire-device)する」に進んでセットアップを完了してください。  
    
    ![ポータルサイトのスクリーンショット例、[デバイスと登録の種類の選択] 画面、デバイスの種類のオプション。](./media/ios-device-type-1909.PNG)  


5. 登録したら、デバイス上のデータを保護する方法を選択します。  
    * [**デバイス全体をセキュリティで保護**する] をタップして、デバイス上のすべてのアプリとデータを保護します。 次に、[[デバイス全体をセキュリティで保護](enroll-your-device-in-intune-ios.md#secure-entire-device)する] にアクセスしてセットアップを完了します。
    * **[セキュリティで保護された作業に関連するアプリとデータのみ**] をタップして、職場アカウントでアクセスするアプリとデータのみを保護します。 次に、[[セキュリティで保護された作業に関連するアプリとデータ](enroll-your-device-in-intune-ios.md#secure-work-related-apps-and-data)] にアクセスします。  

    ![ポータルサイトのスクリーンショット例、[デバイスと登録の種類の選択] 画面、登録の種類のオプション。](./media/ios-enrollment-type-1909.PNG)  


### <a name="secure-entire-device"></a>デバイス全体をセキュリティで保護する  

1. **[デバイスの管理とプライバシー]** 画面で、組織が使用できる、または表示できないデバイス情報の一覧を確認します。 次に **[続行]** をタップします。  


 > [!IMPORTANT]
> 次の手順と画面は、ご使用の iOS のバージョンによって異なります。 ご使用の iOS のバージョンの手順に従います。 

2. Safari によりデバイスでポータル Web サイトが開かれます。 構成プロファイルをダウンロードするように求められたら、 **[許可]** をタップします。 次を実行しているデバイスの場合:  
    * iOS 12.2 以降:ダウンロードが完了したら、 **[閉じる]** をタップします。 次に、手順 3. に進みます。  
    * iOS 12.1 以前: ダウンロードが完了すると、設定アプリに自動的にリダイレクトされます。 手順 4 に進みます。  
 
    誤って **[無視]** をタップすると、ページが更新されます。 ポータル サイト アプリを開くことを求められます。 [ダウンロード] を**もう一度**タップします。

  > [!NOTE]
  > 次の手順で説明されているように、管理プロファイルはダウンロードしてから 8 分以内にインストールする必要があります。 しない場合は、プロファイルが削除され、登録をやり直す必要があります。  

3. ポータルサイトを開くように求められたら、 **[開く**] をタップします。 詳細については、「**管理プロファイルのインストール方法**」を参照してください。  

4. 設定アプリにアクセスし、[ **< 組織名 >** または**プロファイルをダウンロード**して登録する] をタップします。  

    ![[設定] アプリの [組織に登録] オプションのスクリーンショットの例。](./media/enroll-in-organization-ios-1909.PNG)  

   どちらのオプションも表示されない場合は、 **[全般** > **プロファイル & デバイス管理**> **管理プロファイル**] にアクセスします。 それでも管理プロファイルが表示されない場合は、もう一度ダウンロードする必要があります。  

5. **[インストール]** をタップします。  
    
6. デバイスのパスワードを入力します。 次に **[インストール]** をタップします。    

7. 次の画面は、デバイス管理に関する標準のシステム警告です。 インストールを続行するには、 **[インストール]** をタップします。 リモート管理を信頼するように求められたら、 **[信頼]** をタップします。  

8. インストールが完了したら、 **[完了]** をタップします。 プロファイルがインストールされたことを確認するには、 **[プロファイルとデバイスの管理]** 設定に移動します。 **[モバイル デバイス管理]** の下にプロファイルが一覧表示されるはずです。   

    ![管理プロファイルを示す設定アプリの [プロファイルとデバイスの管理] のスクリーンショット例](./media/ios-12-cp-enroll-1904.PNG)  

9. ポータル サイト アプリに戻ります。 ポータル サイトでデバイスの同期と設定が開始されます。 ポータル サイトで追加のデバイス設定を更新するように求められる場合があります。 その場合は、 **[続行]** をタップします。  

10. リスト内のすべての項目に緑色のチェックマークが表示されると、設定が完了したことがわかります。 **[完了]** をタップします。   

> [!Note]
> 組織で音声およびデータの制限を監視している場合、または会社所有のデバイスを提供している場合は、さらにいくつか手順を完了するがあります。 **Datalert** アプリのインストールを求められたら、[通信費管理サービスへのデバイスの登録](enroll-your-device-with-telecom-expense-management-ios.md)に関するページを参照してください。 組織が Apple の Device Enrollment Program に参加している場合は、[会社所有のデバイスを登録する方法](enroll-your-device-dep-ios.md)を見つけてください。  

### <a name="secure-work-related-apps-and-data"></a>作業に関連するアプリとデータをセキュリティで保護する  
1. **[Microsoft Authenticator のダウンロード]** 画面が表示されます (既に認証子を持っている場合は、この画面は表示されず、手順2に進みます)。  
    1. **App Store からダウンロード**する。
    2. App Store が開いたら、アプリをインストールします。 
    3. ポータルサイトに戻り、 **[続行]** をタップします。    
    
   Microsoft Authenticator をインストールした後は、アプリで他の操作を行う必要はありません。 デバイスに存在する必要があるだけです。 

   ![ポータルサイトのスクリーンショットの例、"Download Microsoft Authenticator" 画面。](./media/download-ms-authenticator-1909.PNG)  

2. **[デバイスの管理とプライバシー]** 画面で、組織が使用できる、または表示できないデバイス情報の一覧を確認します。 次に **[続行]** をタップします。  


 > [!IMPORTANT]
> 次の手順と画面は、ご使用の iOS のバージョンによって異なります。 ご使用の iOS のバージョンの手順に従います。 

3. Safari によりデバイスでポータル Web サイトが開かれます。 構成プロファイルをダウンロードするように求められたら、 **[許可]** をタップします。 次を実行しているデバイスの場合:  
    * iOS 12.2 以降:ダウンロードが完了したら、 **[閉じる]** をタップします。 次に、手順 4 に進みます。  
    * iOS 12.1 以前: ダウンロードが完了すると、設定アプリに自動的にリダイレクトされます。 手順 5 に進みます。  
 
    誤って **[無視]** をタップすると、ページが更新されます。 ポータル サイト アプリを開くことを求められます。 アプリから **[Download again]\(再度ダウンロード\)** をタップできます。

  > [!NOTE]
  > 次の手順で説明されているように、管理プロファイルはダウンロードしてから 8 分以内にインストールする必要があります。 しない場合は、プロファイルが削除され、登録をやり直す必要があります。  

4. ポータルサイトを開くように求められたら、 **[開く**] をタップします。 詳細については、「**管理プロファイルのインストール方法**」を参照してください。 

5. 設定アプリにアクセスし、[ **< 組織名 >** または**プロファイルをダウンロード**して登録する] をタップします。  

    ![[設定] アプリの [組織に登録] オプションのスクリーンショットの例。](./media/enroll-in-organization-ios-1909.PNG)  

   どちらのオプションも表示されない場合は、 **[全般** > **プロファイル & デバイス管理**> **管理プロファイル**] にアクセスします。 それでも管理プロファイルが表示されない場合は、もう一度ダウンロードする必要があります。   


6. **[ユーザー登録]** 画面で、 **[iPhone の登録**] をタップします。  

    ![[設定] アプリの [ユーザー登録] 画面で、[登録] ボタンを強調表示したスクリーンショットの例。](./media/user-enrollment-information-1909.PNG)  

7. デバイスのパスワードを入力します。 次に **[インストール]** をタップします。  

8. **[サインイン]** 画面で、管理対象の Apple ID のパスワードを入力します。 ほとんどの場合、これらの資格情報は、組織が別の資格情報のセットを提供していない限り、職場または学校アカウントへのサインインに使用するものと同じです。 
9. **サインインを**タップします。  
10. プロファイルがインストールされた後、画面に成功メッセージが表示されます。 プロファイルがインストールされていることを確認するには、 **プロファイル & デバイス管理** 設定 にアクセスします。  **[モバイル デバイス管理]** の下にプロファイルが一覧表示されるはずです。  

    ![管理プロファイルを示す設定アプリの [プロファイルとデバイスの管理] のスクリーンショット例](./media/ios-12-cp-enroll-1904.PNG)  

11. ポータル サイト アプリに戻ります。 ポータル サイトでデバイスの同期と設定が開始されます。 ポータル サイトで追加のデバイス設定を更新するように求められる場合があります。 その場合は、 **[続行]** をタップします。    

12. リスト内のすべての項目に緑色のチェックマークが表示されると、設定が完了したことがわかります。  **完了**しました。  

## <a name="it-administrator-support"></a>IT 管理者のサポート  
デバイス登録中に問題に遭遇した IT 管理者は、「[Troubleshooting iOS device enrollment problems in Microsoft Intune (Microsoft Intune の iOS デバイスの登録に関する問題のトラブルシューティング)](https://support.microsoft.com/en-us/help/4039809)」を参照してください。 この記事では、一般的なエラー、その原因、解決する手順の一覧が示されています。  

## <a name="next-steps"></a>次のステップ  
職場または学校で役立つアプリを検索します。 ポータル サイトを通じて[アプリがどのように使用可能になるか](use-managed-apps-on-your-device-ios.md)を学習します。  

サポートが必要な場合は、 会社のサポートに問い合わせてください。 連絡先の情報は、[会社のポータル Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)でわかります。  

---
title: Microsoft Intune のサポートを受ける方法
titleSuffix: Microsoft Intune
description: Microsoft Intune の有料サブスクリプションと試用版サブスクリプションについて、オンラインと電話によるサポートを受けます。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c4d40d3f15fe23511f3f15f7c13181a0fa72f6b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726519"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Microsoft Intune のサポートを受ける方法  

[!INCLUDE [azure_portal](../../intune-classic/includes/note-for-both-portals.md)]  
  
Microsoft サポートは、Microsoft Intune に世界的な技術、購入前、請求、およびサブスクリプションのサポートを提供しています。 有料サブスクリプションと試用版サブスクリプションについて、オンラインと電話によるサポートを利用できます。 オンライン テクニカル サポートは、英語と日本語で提供されています。 電話によるサポートとオンライン課金サポートは、他の言語でも利用できます。

Intune 管理者は、 **[ヘルプとサポート]** オプションを使用して、Azure portal から Intune 用のオンライン サポート チケットを提出することができます。 サポート インシデントを作成して管理するには、"*アクション*" **microsoft.office365.supportTickets/tickets/manage** が含まれる Azure Active Directory (Azure AD) ロールをアカウントが持っている必要があります。 サポート チケットを作成するために必要な Azure AD のロールとアクセス許可については、[Azure Active Directory での管理者ロール](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)に関するページを参照してください。  

>[!IMPORTANT]  
> Intune と連携するサードパーティ製品 (Saaswedo、Cisco、Lookout など) のテクニカル サポートについては、まず、その製品の提供元に連絡してください。 Intune サポート要求を開始する前に、その他の製品が正しく構成されていることを確認します。
>
> Microsoft Intune に関連する問題のトラブルシューティングについては、Intune のドキュメントの[トラブルシューティングに関するセクション](help-desk-operators.md)を参照してください。

## <a name="known-issues-for-creating-support-incidents"></a>サポート インシデントの作成に関する既知の問題  

アカウントに必要なアクセス許可があるが、[ヘルプとサポート] に正常にアクセスできないか、サポート インシデントを作成または管理できない場合は、次の既知の問題と解決策を確認してください。  
- アカウントのユーザー トークンが古くなっている。 この問題を解決するには、すべてのアクティブなコンソール セッションからサインアウトし、もう一度サインインしてから、サポート インシデントを作成または管理してみます。 
- アクティブなセッションが複数存在する。 複数のユーザーまたはセッションを使用してサインインしている場合は、1 つのコンソールを除くすべてのセッションからサインアウトします。 次に、1 つのアクティブなセッションを使用して、サポート インシデントを作成または管理してみます。

アクセスの問題を解決するために必要になる可能性がある追加のアクションは、次のとおりです。
- アクティブなブラウザー セッションのすべての cookie をクリアしてから、サポート インシデントの作成または管理を再試行します。
- InPrivate ブラウズ セッションを使用して Intune にサインインし、サポート インシデントを作成または管理してみます。  

前述の回避策で問題が解決しない場合は、[Microsoft 365 管理センター](https://admin.microsoft.com)にアクセスし、そこからサポート チケットを作成します。 現在、夏の終わりに使用可能になる予定の修正プログラムを作成中です。  

## <a name="help-and-support-experience"></a>ヘルプとサポート エクスペリエンス  

Intune のヘルプとサポート エクスペリエンスは、[Microsoft 365 デバイス管理ポータル](https://devicemanagement.microsoft.com)、および Azure portal の Intune のすべてのブレード (またはページ) から使用できます。 

![Intune のブレード](./media/get-support/intune-blades.png)


"*ヘルプとサポート*" のエクスペリエンスは、[Microsoft 365 管理センター](https://admin.microsoft.com/)で表示されるエクスペリエンスと似ており、Azure の他のサービスには残っている以前の "*ヘルプとサポート*" に代わるものです。 

[ヘルプとサポート] にアクセスするには、次のオプションを使用します。  
- **デバイス管理ダッシュボード:**
  - Intune の機能領域を選択した後、 **[ヘルプとサポート]** のオプションを選択します。
  - デバイス管理ポータルの任意のノードから、 **[?]** アイコン (ポータルの右上隅) を選択し、ドロップダウンを使用してヘルプの必要なサービスを選択します。 **[?]** アイコン (デバイス管理ポータル) では複数のサービスがサポートされており、支援が必要な特定のサービスを選択する必要があります。  

    ![サービスを選択する](./media/get-support/select-a-service.png)

    サービスを選択し、そのサービスの *[ヘルプとサービス]* ページが表示されたら、ヘルプの必要な特定の問題についての[詳細を指定する](#specify-details-about-an-issue)ことができます。  

    検索結果がサービスに対して予想されるものと一致しない場合は、正しいサービスを選択したことを確認してください。 サービスの選択は、 *[ヘルプとサポート]* のすぐ後に表示されます。  正しいサービスが選択されていない場合は、 *[サービスの選択]* をクリックして、サービス選択ドロップダウンに戻ります。   

    ![サービスを確認する](./media/get-support/confirm-your-service-selection.png) 


- **Azure portal で:**
  - Intune の任意のブレードまたはページから **[ヘルプとサポート]** を選択する

  Azure portal で、 **[?]** アイコン (右上隅)、または左側のナビゲーション ウィンドウの **[ヘルプとサポート]** を選択すると、Azure の *[ヘルプとサポート]* が開きます。 Azure の *[ヘルプとサポート]* からは、Intune のサポート インシデントを直接開くことはできませんが、次の操作を行うことで、Intune の *[ヘルプとサポート]* ページに移動できます。 
  1. [新しいサポート要求] を選択します。
  2. [問題の種類] で [技術] を指定します。
  3. [サービス] で [Microsoft Intune] を指定します。
  4. Intune のヘルプとサポート ページのリンクを選択します。

> [!NOTE]  
> Intune のインスタンスが Government Compute Cloud (GCC) でホストされている場合 (Azure Government のようなソブリン クラウドとも呼ばれます)、後の「Intune での Government Compute Cloud のサポート」を参照してください。 Intune の *[ヘルプとサポート]* エクスペリエンスは、今年の後半まで GCC では使用できません。 


*[ヘルプとサポート]* を開くとポータルに表示されるビューは、アクティブなサポート インシデントがあるかどうか、および Premier サポートをお持ちのときは追加の要素とオプションによって、異なります。
- **アクティブなサポート インシデントなし**: 次のデバイス管理ダッシュボードの画像のような、 **[ヘルプが必要ですか?]** ページが表示されます。  
- **アクティブなサポート インシデントあり**: [サポート チケット](#view-support-cases) ページが表示され、アクティブなインシデントの一覧が示されます。  
- **Premier サポート契約**: エクスペリエンスは最初の 2 つのオプションと同じですが、[ヘルプが必要ですか?] ページに次の追加要素が表示されます。 
  - ページ タイトル **[ヘルプが必要ですか?]** の後に、Premier サポートのバナーが表示されます。  
    ![Premier サポート バナー](./media/get-support/premier-banner.png)
  - ページの **[サポートの利用]** セクションでは、電話によるサービス要求を作成するときの最初の**重大度**レベルを設定できます。


![デバイス管理ダッシュボードと [ヘルプが必要ですか?] ページ](./media/get-support/help-support-dashboard.png)

このビューでは、以下の操作を行うことができます。

1. ヘルプが必要な特定の問題について[詳細を指定する](#specify-details-about-an-issue)  
2. 指定した詳細に基づき、[状況依存のヘルプ](#view-context-sensitive-help)と関連ソリューションを表示する  
3. 電子メールや電話を利用して[サポートを受ける](#get-support)  
4. この新しいワークフローを利用して前に[サポート ケース](#view-support-cases)を登録している場合、それを表示する  

### <a name="specify-details-about-an-issue"></a>問題に関する詳細を指定する 

新しいエクスペリエンスでサポートされている場所から [ヘルプとサポート] を開くと、 **[ヘルプが必要ですか?]** ページが開きます。 このページで、問題の詳細を指定できます。 詳細を入力すると、使用したキーワードに基づき、よくある問い合わせがコンソールから提示されます。 提案を選択するか、自分で問題を説明します。 自分で説明を入力する場合、 **[ヘルプを表示]** を選択して送信します。 問い合わせを送信すると、問題の解決に役立つ可能性がある状況依存情報がコンソールから返されます。

次は、送信することがある問い合わせの例です。
  
- *iOS デバイスを復元できません*  
- *条件付きアクセス ポリシーを作成できません*  

![[ヘルプが必要ですか?] ページで問題を指定する](./media/get-support/describe-the-issue.png)

### <a name="view-context-sensitive-help"></a>状況依存のヘルプを表示する 

提案を選択するか、独自の問い合わせを送信すると、 **[ソリューションの表示]** の下に状況依存の結果が表示されます。 これらの結果には、Intune 固有のセルフヘルプ ガイダンスと、クエリ条件に基づく Web 検索から返された追加の結果の両方が含まれます。  
![結果の表示](./media/get-support/view-results.png)

### <a name="get-support"></a>サポートを受ける 

セルフヘルプまたは Web ベースのガイダンスで問題が解決されない場合は、コンソールを使用して、電子メールまたは電話でサポートを受けてください。  
**[ヘルプが必要ですか?]** ページで、使用するオプションを選択します。  

  > [!NOTE] 
  > サポートのメールによる要求は、テナントによっては使用できない場合があります。  

- 電子メールで依頼する場合、自分の電子メール アドレスを入力してください。任意で、提出に添付ファイルを追加できます。 **[送信]** を選択し、依頼を登録します。 

  ![電子メールによる依頼](./media/get-support/email-support.png)
  
- 電話で依頼する場合、自分の電話番号を入力してください。 任意で、自分の電子メール アドレスを含めたり、提出に添付ファイルを追加したりできます。 [電話で連絡] を選択し、依頼を提出します。  



   ![電話で依頼](./media/get-support/phone-support.png)

**Premier サポート**:  
Premier サポート契約をお持ちの場合は、電話サポート インシデント作成と同じオプションがあります。 サポート コールバックに対する**重大度**を指定し、ミッション クリティカル契約に対するサポート チケットの作成を選択することもできます。  

![Premier サポートのオプション](./media/get-support/premier-phone-support-options.png)


### <a name="view-support-cases"></a>サポート ケースを表示する  

[履歴] ボタンを選択すると、作成したサポート インシデントが表示されます。  

![サポート ケースを表示する](./media/get-support/view-support-tickets.png)

- 新しいワークフローを使用して登録したサポート ケースだけがこのワークフロー内から表示されます。 サポート ケースを表示するには、デバイス管理コンソール、または Azure portal にある Intune のブレードで、[ヘルプとサポート] ビューを使用します。 これらのケースには 8 桁の数字が与えられます。 これらのケースは Microsoft 365 管理センターからも表示できます。  

- Intune のヘルプとサポート エクスペリエンスを使用していないときに開いたケースは、変更ありません。 そのようなケースを表示するには、Intune エクスペリエンスに含まれない [ヘルプとサポート] ビュー、またはデバイス管理ダッシュボードを使用する必要があります。 これらのケースには **117** または **118** で始まる 15 桁の数字が与えられます。 管理共有を表示するには

    1. Intune 管理者資格情報を使用して Azure (<https://portal.azure.com>) にサインインして、 *[?]* を選択します。 アイコンを選択し、 *[ヘルプとサポート]* を選択して、[Azure のヘルプとサポート](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)のページに移動します。

    2. **ヘルプとサポート**のページでは、**最近のサポート要求**の一覧を表示し、さらにそれらを選択して詳細を確認することができます。
 

## <a name="azure-help--support-experience"></a>Azure のヘルプとサポート エクスペリエンス 

左側のナビゲーション ウィンドウの **[ヘルプとサポート]** を使用するか、または **[?]** オプション (Azure portal の右上隅) を使用すると、Intune のヘルプとサポート エクスペリエンスとは異なる Azure のヘルプとサポート エクスペリエンスが開きます。  

2019 年 4 月以降、サブスクリプションが Government Compute Cloud (GCC) のものでない限り、Azure の *[ヘルプとサポート]* エクスペリエンスにアクセスして、Intune のサポートを受けることはできません。  

Intune のインスタンスが GCC 上で実行されていない場合は、Azure の *[ヘルプとサポート]* に移動すると、サポート インシデントを作成して管理するために Intune の *[ヘルプとサポート]* エクスペリエンスにリダイレクトされます。  


## <a name="intune-support-for-government-compute-cloud"></a>Intune での Government Compute Cloud のサポート  

お使いの Intune サブスクリプションが Government Compute Cloud (GCC) (Azure Government のようなソブリン クラウドとも呼ばれます) でホストされている場合、Intune の新しいヘルプとサポート エクスペリエンスにはまだアクセスできません。  代わりに、次の情報を使用して Intune のサポートを受けてください。 


### <a name="create-an-online-support-ticket"></a>オンライン サポート チケットの作成 

>[!IMPORTANT]    
> "*ヘルプとサポート*" が GCC ではまだ使用できない新しいシステムに移行した場合、サポート インシデントを作成すると、ポータルでは 15 桁の識別番号を使用するサポート ケースが識別されます。 15 桁のケースが作成されると、そのケースのミラーが Microsoft サポート用に作成されます。 このミラー ケースは、8 桁のケース ID を使用して新しいサポート システムで作成され、サポート サービスにより、サポート インシデントに関するすべての作業の追跡と通信のために使用されます。 15 桁のケースが作成されるとすぐに、サポート サービスで使用されるミラー化されたサポート ケースの 8 桁の番号を示す電子メールが届きます。  
> 
> サポート担当者は、8 桁のサポート ケースで作業と通信を行い、通信のログ記録とインシデントの進行状況の追跡には 8 桁のサポート ケースのみを使用します。 したがって、その 8 桁のサポート ケースから、ケースの作業の追跡記録となる電子メールの更新を受け取ります。 15 桁のサポート インシデントには、詳細情報は記録されません。 サポートが終了し、8 桁のサポート ケースが閉じられると、その状態は、Azure portal 内から表示できる 15 桁のサポート ケースに反映されます。  15 桁のサポート ケースについては、他の更新や状態の変更は想定されていません。  
> 
> 今年の後半にサポート ツールの移行が完了すると、Government Cloud でホストされている Intune のサポート エクスペリエンスは、パブリック クラウドでホストされている Intune サブスクリプションで現在利用可能な既定の "*ヘルプとサポート*" エクスペリエンスと似たものになります。  


1. Intune 管理者資格情報を使用して Azure portal (<https://portal.azure.com>) にサインインして、 **[?]** を選択します。 アイコンを選択し、 **[ヘルプとサポート]** を選択して、[Azure のヘルプとサポート](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)のページに移動します。

   ![[ヘルプとサポート] のリンクが強調表示された疑問符マークの画像](./media/get-support/azure-get-support.png)

2. Azure の **[ヘルプとサポート]** のページ上で、 **[新しいサポート要求]** を選択します。

   ![[ヘルプとサポート] ページで [新しいサポート要求] のリンクが強調表示された画像](./media/get-support/azure-support-ticket-link.png)

3. Intune のほとんどのテクニカル サポートの問題では、 **[基本]** タブ上で、次のオプションを選択します。
   - **問題の種類**: **テクニカル**
   - **サブスクリプション**: <"*お使いのサブスクリプション*">
   - **サービス**:**Microsoft Intune**
   - **[問題の種類]** : ドロップダウン メニューから、問題の種類を選択します。
   - **[問題のサブタイプ]** : ドロップダウン メニューから、問題のサブタイプを選択します。
   - **[件名]** : ヘルプが必要な問題を簡単に説明します。

   ![[ヘルプとサポート] の [基本] タブの画像 - [新しいサポート要求] ページ](./media/get-support/help-new-support-case-basics.png)

   **[Next: Solutions]\(次へ: ソリューション\)** を選択して続行します。
4. **[ソリューション]** タブ上で、チケットを提出しなくても問題の解決に役立つ可能性がある推奨手順を確認します。 手順を確認した後に、やはりサポート要求を作成することにした場合は、 **[Next: Details]\(次へ: 詳細\)** をクリックします。

   ![[ヘルプとサポート] の [ソリューション] タブの画像 - [新しいサポート要求] ページ](./media/get-support/help-new-support-case-solutions.png)
5. **[詳細]** タブ上で、問題の詳細、サポートの方法、お客様の連絡先情報を入力してから、 **[Next: Review + create]\(次へ: 確認と作成\)** をクリックします。

   ![[ヘルプとサポート] の [詳細] タブの画像 - [新しいサポート要求] ページ](./media/get-support/help-new-support-case-details.png)
6. 情報を見直して、正しいことを確認してから、 **[作成]** を選択してサポート要求を送信します。

   ![[新しいサポート要求] ページの [review + create]\(確認と作成\) タブの画像](./media/get-support/help-new-support-case-create.png)

>[!IMPORTANT]
>請求やサブスクリプションの質問がある場合は、ケースを開いて [Microsoft 365 管理センター](https://admin.microsoft.com/Support/SupportEntry.aspx)からサポートを受けることができます。

### <a name="view-support-requests"></a>サポート要求を表示する  

Azure portal 内からサポート要求を表示できます。 ただし、利用できる情報は限られます。  インシデントを表示するには: 

1. Intune 管理者資格情報を使用して Azure (<https://portal.azure.com>) にサインインして、 **[?]** を選択します。 アイコンを選択し、 **[ヘルプとサポート]** を選択して、[Azure のヘルプとサポート](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)のページに移動します。

2. **[ヘルプとサポート]** ページでは、 **[最近のサポート要求]** の一覧を見ることができます。

   > [!IMPORTANT]  
   > Government Compute Cloud のお客様は、15 桁のサポート ケース番号とインシデントの状態のみを表示できます。 ケースに関するすべての通信および作業またはアラートの追跡はメールによって送信され、Intune コンソール内から開かれたサポート ケースのミラーとして作成された 8 桁のサポート ケース番号が参照されています。   

## <a name="additional-resources"></a>その他のリソース  

- [課金とサブスクリプション管理のサポート](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [ボリューム ライセンス](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Intune の問題のトラブルシューティング](help-desk-operators.md)
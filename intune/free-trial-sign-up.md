---
title: "30 日間の無料試用版にサインアップする"
titleSuffix: Intune on Azure
description: "Azure での Intune にサインアップする方法について説明します。\""
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7dafdb974dd975eaa7f3268119de6c047c50f858
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2017
---
# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal"></a>Azure Portal の Microsoft Intune 無料試用版にサインアップする


この記事では、Azure Portal の Intune スタンドアロンの試用版にサインアップする方法について説明します。

1. [Intune サインアップ](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) ページにアクセスしてフォームに入力し、試用版サブスクリプションにサインアップします。
account-sign-up.md

  IT 運用チームやユーザーの大半が自分と異なるロケールに属している場合は、そのロケールを **[Where's your company located? (会社の所在地はどこですか?)]** で選択することをお勧めします。

2. サインアップ プロセスの最後に、新しいアカウントの情報を含むメッセージが表示されます。 <br/> ![アカウント情報の画像](./media/2-end-of-sign-up-process.png) <br/>この時点で **[You're ready to go]\(準備完了\)** をクリックすると、Office 365 管理センターが表示されるので、そこでテスト環境にユーザーを追加できます。 <br/><br/>ただし、Intune Azure Portal に直接アクセスしたい場合は、新しいブラウザー ウィンドウを開き、アドレス バーに「**https://portal.azure.com**」と入力します。 Azure サインイン ページが表示されるので、提供されている資格情報を使用してサインインします。 Intune 試用版にサインインする際は常にこのアドレスを使用してください。 <br/> ![Azure Portal のサインイン ページの画像](./media/azure-portal-signin.png)

Intune Azure Portal に初めてサインオンすると、Azure ダッシュボードに Intune が表示されないことがあります。 Intune サービスを Azure ダッシュボードに追加するには:
1. ダッシュボードの左にある Azure サービスの一覧で **[その他のサービス >]** を選択し、検索ボックスに「**Intune**」と入力します。
2. 一覧から **[Intune]** を選択し、星を選択してサービスの一覧にサービスを追加します。<br/> ![サービス一覧から Intune を選択する画像](./media/azure-add-intune1.png)
3. サービス一覧から **[Intune]** を選択し、Intune ダッシュボードを開きます。

試用版にサインアップすると、アカウント情報の記載された電子メール メッセージが、サインアップ プロセス中に指定した電子メール アドレスに送信されます。 このメールで、試用版がアクティブになったことが確認されます。



## <a name="keeping-the-admin-experiences-straight"></a>管理者の経験を続ける


Intune Azure Portal で使用するポータルは 3 つあります。
- Azure ([portal.azure.com](https://portal.azure.com)) の Intune ダッシュボードでは、[Azure Portal にある Intune の各機能](what-is-intune.md)を確認できます。
- Office 365 管理センター ([portal.office.com](https://portal.office.com)) では、ユーザーの追加と管理ができます (Azure Active Directory を使用していない場合)。 また、課金やサポートなど、アカウントのその他の要素を管理することもできます。
- クラシック Intune 管理コンソール ([manage.microsoft.com](https://manage.microsoft.com)) では、まだ Azure に追加されていない機能を確認できます。

通常、次のように、Intune ダッシュボードで作業します。 これがグループ、ポリシー、デバイス、アプリを設定し、管理する場所となります。

ダッシュボードからクラシック Intune 管理コンソールを開くには、ダッシュボードの一番上にある **[クラシック ポータル]** を選択します。

Intune Azure Portal に戻るには、ブラウザーのアドレス バーに「https://portal.azure.com」と入力し、サービス一覧から **[Intune]** をもう一度選択します。

 ![Intune ダッシュボードの画像](./media/intune-azure-dashboard.png)


次に示すように、ユーザーを追加したり、ユーザーやアカウントのその他の設定 (請求やサポートなど) を管理したりするときは、Office 365 管理センターを利用します。

![Office 365 管理センターの画像](./media/office-admin-center.png)

Office 365 管理センターから Intune ダッシュボードに移動するには、ブラウザーのアドレス バーに「https://portal.azure.com」と入力します。 サービス一覧から **[Intune]** を選択します。

Intune から Office 365 管理センターに戻るには、ブラウザーのアドレス バーに「https://portal.office.com」と入力します。 既に Intune にログインしている場合は、Office 365 管理センターがそのまま表示されます。

## <a name="next-steps"></a>次のステップ

### <a name="intune-on-azure"></a>Azure での Intune
詳細については、[Azure Portal での Intune](what-is-intune.md) に関するページを参照してください。
### <a name="classic-intune"></a>クラシック Intune
評価シナリオ: [Microsoft Intune でモバイル デバイス管理を評価する](https://docs.microsoft.com/intune-classic/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>他の製品との統合
Intune で Azure Active Directory ユーザー アカウントを使用する方法に関するページ:
- [ID の要件](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [ディレクトリ同期の要件](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [多要素認証の要件](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

[Intune と System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management) を使用する方法に関するページ
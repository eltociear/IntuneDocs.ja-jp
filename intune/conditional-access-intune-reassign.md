---
title: "条件付きアクセス ポリシーを Intune クラシック ポータルから新しい Azure Portal に移行する"
titleSuffix: Intune on Azure
description: "条件付きアクセス ポリシーを Intune クラシック ポータルから新しい Azure Portal に移行します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>条件付きアクセス ポリシーを Intune クラシック ポータルから新しい Azure Portal に再割り当てする

新しい Azure Portal 以降の条件付きアクセスは、アプリケーションごとの複数のポリシーと詳細なカスタマイズ機能のサポートを提供します。

## <a name="before-you-begin"></a>始める前に

新しい Azure Portal に移行する準備ができた場合、以下の手順で、Intune クラシック ポータルで作成した条件付きアクセス ポリシーを再割り当てすることができます。

- Intune クラシック ポータルで前に作成した条件付きアクセス ポリシーを収集し、後で再割り当てする必要がある設定を把握できるようにします。

- このトピックの手順に従って、新しい Azure Portal でポリシーを再作成します。

- 新しい Azure Portal で新しいポリシーが意図したとおりに動作することを確認した後、Intune クラシック コンソールで条件付きポリシーを無効にします。
<br /><br />
    - Intune クラシック ポータルで条件付きアクセス ポリシーを**無効にする前に**、新しいポリシーへのユーザー移行方法を計画します。 これには 2 つの方法があります。
<br /><br />
        - **同じ包含グループを使って新しい Azure Portal で作成されたポリシーを適用し、新しい除外グループを作成して Intune クラシック ポータルによって適用されたポリシーで使います**。
            - クラシック ポータルで指定されている除外グループにユーザーを段階的に移動します。  これにより、Intune クラシック ポータルの対象になっているポリシーが適用されないようにします。 Intune クラシック ポータルで適用されていたポリシーに加えて、新しい Azure Portal の同じユーザー グループを対象に作成されたポリシーが適用されます。 
<br /><br />
        - **新しい Azure Portal の条件付きアクセス ポリシーを対象とする新しいグループを作成します**。 この方法を選んだ場合、次のことを行う必要があります。
            - Intune クラシック ポータルで条件付きアクセス ポリシーの対象になっていたセキュリティ グループからユーザーを段階的に削除します。
            - これらのユーザーに対して新しいポリシーが動作することを確認した後、Intune クラシック ポータルでポリシーを無効にできます。 
<br /><br />
- Intune クラシック ポータルで Exchange Active Sync (EAS) を使うように条件付きアクセス ポリシーの設定を構成してあった場合は、[このトピックの手順](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients)を参照して、**新しい Azure Portal で EAS 条件付きアクセス ポリシーの設定を再割り当て**します。

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Intune クラシック ポータルでデバイス ベースの条件付きアクセス ポリシーを確認するには

1.  [Intune クラシック ポータル](https://manage.microsoft.com)に移動し、資格情報でサインインします。

2.  左側のメニューから **[ポリシー]** を選びます。

3.  **[条件付きアクセス]** を選んだ後、条件付きアクセス ポリシーを作成した対象の Microsoft クラウド サービス (Exchange Online、SharePoint Online など) を選びます。

4.  条件付きアクセス設定を記録し、それを参考にして、新しい Azure Portal で同じ条件付きアクセス ポリシーを作成します。

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>連携するアプリ ベースとデバイス ベースの条件付きアクセス ポリシー

新しい Azure Portal の **[Intune アプリ保護]** ブレードで、管理者は、Intune アプリ保護ポリシーをサポートするアプリのみが会社リソースへのアクセスを許可されるように、アプリ ベースの条件付きルールを設定できます。 アプリ ベースの条件付きアクセス ポリシーとデバイス ベースの条件付きアクセス ポリシーを併用することができます。 デバイス ベースとアプリ ベースの条件付きポリシーの組み合わせを、両方必要 (論理 AND) または一方だけでも可能 (論理 OR) にできます。 条件付きアクセス ポリシーの要件に応じて次のようになります。

- 準拠したデバイスが必要、**かつ**、承認されたアプリを使用。
    - [Azure AD の条件付きアクセス ブレード](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)と [Intune のアプリ保護ブレード](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0)を使って、条件付きアクセス ポリシーを設定する必要があります。
<br /><br />
- 準拠したデバイスが必要、**または**、承認されたアプリを使用。
    - [Intune クラシック ポータル](https://manage.microsoft.com)と [Intune のアプリ保護ブレード](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0)を使って、条件付きアクセス ポリシーを設定する必要があります。

> [!TIP] 
> このトピックでは、Intune クラシック ポータルと新しい Azure Portal のユーザー エクスペリエンスを比較するスクリーンショットを示します。

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Intune のデバイス ベース条件付きアクセス ポリシーを再割り当てするには

1. [新しい Azure Portal の [条件付きアクセス]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) に移動し、資格情報でサインインします。

2. **[新しいポリシー]** を選びます。

3. ポリシーの名前を指定します。

4. 新しい条件付きアクセス ポリシーの対象として、**[割り当て]** セクションで **[ユーザーとグループ]** を選びます。
    
    ![Intune クラシック ポータルと新しい Azure Portal のユーザー グループ UI の比較](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Intune クラシック ポータルですべてのユーザーを選択していた場合は、すべてのユーザーを含めます。 同じことがグループにも当てはまり、グループを選択していた場合は、**[ユーザーとグループの選択]** を選んでそれらのグループを含める必要があります。 さらに、Intune クラシック ポータルで **[除外グループ]** オプションを選んであった場合は、新しい Azure Portal でもそのグループを除外する必要があります。

5. グループを選んだ後、**[選択]** をクリックし、**[完了]** をクリックします。

6. **[割り当て]** セクションで **[クラウド アプリ]** を選びます。

7. **[クラウド アプリ]** ブレードで、**[アプリを選択]** を選びます。

8. 新しい条件付きアクセス ポリシーを適用するアプリを選び、**[選択]** をクリックします。

9. **[完了]** をクリックします。

    ![Intune クラシック ポータルと新しい Azure Portal のクラウド アプリ UI の比較](./media/reassign-ca-3.png)

    > [!TIP] 
    > 同じポリシーを複数のアプリに適用してある場合は、新しい Azure Portal では 1 つのポリシーに統合することができます。

10. **[割り当て]** セクションで **[条件]** を選びます。

11. **[条件]** ブレードで **[デバイス プラットフォーム]** を選び、該当するデバイス プラットフォームを選びます。

12. デバイス プラットフォームの選択が終わったら、**[完了]** を 2 回クリックします。

    ![Intune クラシック ポータルと新しい Azure Portal のデバイス プラットフォーム UI の比較](./media/reassign-ca-4.png)

    > [!TIP] 
    > Intune クラシック ポータルで個別のプラットフォームを選択してあった場合は、新しい Azure Portal でも個別のプラットフォームを選びます。

    > [!NOTE] 
    > 後で Windows に対するドメイン参加または準拠オプションを指定できます。

13. **[割り当て]** セクションで **[条件]** を選びます。

14. **[条件]** ブレードで **[クライアント アプリ]** を選び、該当するクライアント アプリを選びます。

15. クライアント アプリの選択が終わったら、**[完了]** を 2 回クリックします。

    ![Intune クラシック ポータルと新しい Azure Portal のクライアント アプリ UI の比較](./media/reassign-ca-6.png)

16. Intune クラシック ポータルでブラウザーの設定を選択していた場合は、新しい Azure Portal で **[ブラウザー]** と **[モバイル アプリとデスクトップ クライアント]** の両方を選びます。 Intune クラシック ポータルでブラウザーの設定を選択していなかった場合は、**[モバイル アプリとデスクトップ クライアント]** だけを選びます。 

17. **[アクセス制御]** セクションで **[許可]** を選びます。

18. **[Grant Access Controls\(アクセス制御の許可\)]** で **[デバイスは準拠としてマーク済みである必要があります]** をオンにし、**[選択]** をクリックします。

19. ドメインに参加している Windows デバイスを要求するポリシーがあり、Intune に登録された準拠している Windows デバイスも許可する場合は、**[ドメインに参加しているデバイスが必要です]** および **[デバイスは準拠としてマーク済みである必要があります]** と共に **[選択したコントロールのいずれかが必要]** をオンにします。

20. Intune に登録された準拠している Windows デバイスを許可しない場合は、現在のポリシーから Windows ポリシーを除外した後、**[デバイス プラットフォーム]** を **[Windows]** に設定したポリシーを別に作成し、他の条件は上記と同じように設定して、**[Grant Access Controls\(アクセス制御の許可\)]** で **[ドメインに参加しているデバイスが必要です]** をオンにします。

21. **[新規]** 条件付きアクセス ポリシー ブレードで **[ポリシーを有効にする]** をオンにして、**[作成]** をクリックします。

    ![Intune クラシック ポータルと新しい Azure Portal の CA ポリシー有効化 UI の比較](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>EAS クライアントに対する Intune のデバイス ベース条件付きアクセス ポリシーを再割り当てするには

Intune クラシック ポータルで Exchange Online のポリシーの一部として Exchange Active Sync (EAS) の設定を構成していた場合は、新しい Azure Portal で 2 番目の条件付きアクセス ポリシーを作成する必要があります。

1. [新しい Azure Portal の [条件付きアクセス]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) に移動し、資格情報でサインインします。

2. **[新しいポリシー]** を選びます。

3. ポリシーの名前を指定します。

4. 新しい条件付きアクセス ポリシーの対象として、**[割り当て]** セクションで **[ユーザーとグループ]** を選びます。

    ![Intune クラシック ポータルと新しい Azure Portal のユーザー グループ UI の比較](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Intune クラシック ポータルですべてのユーザーを選択していた場合は、すべてのユーザーを含めます。 同じことがグループにも当てはまり、グループを選択していた場合は、**[ユーザーとグループの選択]** を選んでそれらのグループを含める必要があります。 さらに、Intune クラシック ポータルで **[除外グループ]** オプションを選んであった場合は、新しい Azure Portal でもそのグループを除外する必要があります。

5. グループを選んだ後、**[選択]** をクリックし、**[完了]** をクリックします。

6. **[割り当て]** セクションで **[クラウド アプリ]** を選びます。

7. **[クラウド アプリ]** ブレードで **[選択されているアプリ]** をクリックし、**[Exchange Online]** を選び、**[選択]**、**[完了]** の順にクリックします。

    ![Intune クラシック ポータルと新しい Azure Portal のクラウド アプリ UI の比較](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > EAS クライアントの条件付きアクセス ポリシーに他のクラウド アプリを含めることはできません。

8. **[条件]** ブレードで **[クライアント アプリ]** を選び、該当するクライアント アプリを選びます。 Intune でサポートされていないクライアントのブロックを選択してあった場合は、**[サポートされているプラットフォームのみにポリシーを適用する]** オプションを使います。

    ![Intune クラシック ポータルと新しい Azure Portal のクライアント アプリ UI の比較](./media/reassign-ca-15.png)

9. クライアント アプリの選択が終わったら、**[完了]** を 2 回クリックします。

10. **[アクセス制御]** セクションで **[許可]** を選びます。

11. **[Grant Access Controls\(アクセス制御の許可\)]** で **[デバイスは準拠としてマーク済みである必要があります]** をオンにし、**[選択]** をクリックします。

    ![Intune クラシック ポータルと新しい Azure Portal のアクセス許可 UI の比較](./media/reassign-ca-16.png)

12. **[新規]** 条件付きアクセス ポリシー ブレードで **[ポリシーを有効にする]** をオンにして、**[作成]** をクリックします。

    ![Intune クラシック ポータルと新しい Azure Portal の CA ポリシー有効化 UI の比較](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Intune クラシック ポータルで条件付きアクセス ポリシーを無効にする
### <a name="before-you-start"></a>アップグレードを開始する前に

新しい Azure Portal で条件付きアクセス ポリシーの再割り当てを行った後は、Intune クラシック ポータルで以前に作成した条件付きアクセス ポリシーを段階的に無効にすることが重要です。 さらに、同じセキュリティ グループを使って、新しい Azure Portal で作成した条件付きアクセス ポリシーを適用することが必要な場合があります。

- Intune クラシック ポータルで条件付きアクセス ポリシーを無効にする前に、このトピックの「[始める前に](#before-you-begin)」セクションをご覧ください。

### <a name="to-disable-the-conditional-access-policies"></a>条件付きアクセス ポリシーを無効にするには

1.  [Intune クラシック ポータル](https://manage.microsoft.com)に移動し、資格情報でサインインします。

2.  左側のメニューから **[ポリシー]** を選びます。

3.  **[条件付きアクセス]** を選んだ後、条件付きアクセス ポリシーを作成した対象の Microsoft クラウド サービス (Exchange Online、SharePoint Online など) を選びます。

4.  **[条件付きアクセス ポリシーを有効にする]** オプションをオフにした後、**[保存]** をクリックします。

    ![Intune クラシック ポータルで条件付きアクセス ポリシーを無効にする](./media/reassign-ca-18.png)

## <a name="see-also"></a>関連項目

- [Intune での条件付きアクセスの一般的な使用方法](conditional-access-intune-common-ways-use.md)
- [Intune を使用したアプリ ベースの条件付きアクセス](app-based-conditional-access-intune.md)
- [Azure Active Directory の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
---
title: アプリ保護ポリシーを作成して展開する
titleSuffix: Microsoft Intune
description: このトピックでは、Microsoft Intune アプリ保護ポリシー (APP) を作成して割り当てる方法について説明します。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4958a35f3a83fecffacf26421e4c1d797f45ddaa
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940393"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>アプリ保護ポリシーを作成して割り当てる方法

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune アプリ保護ポリシーを作成してユーザーに割り当てる方法について説明します。 このトピックでは、既存のポリシーを変更する方法についても説明します。

## <a name="before-you-begin"></a>始める前に

アプリ保護ポリシーは、場合によっては Intune で管理できないデバイスで実行されているアプリに適用できます。 アプリ保護ポリシーのしくみと Intune のアプリ保護ポリシーでサポートされるシナリオの詳細については、[Microsoft Intune のアプリ保護ポリシー](app-protection-policy.md)に関するページを参照してください。

MAM でサポートされるアプリの一覧については、[MAM アプリの一覧](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)に関するページをご覧ください。

組織の基幹業務 (LOB) アプリを Microsoft Intune に追加してアプリ保護ポリシーを準備する方法について詳しくは、「[Microsoft Intune にアプリを追加する](apps-add.md)」をご覧ください。

## <a name="create-an-app-protection-policy"></a>アプリ保護ポリシーを作成する
1. Intune ポータルで、 **[クライアント アプリ]** 、 **[アプリ保護ポリシー]** の順に選択します。 この選択により、 **[アプリ保護ポリシー]** の詳細が開き、ここで新しいポリシーを作成したり、既存のポリシーを編集したりできます。
2. **[ポリシーを作成する]** を選択します。

   ![[ポリシーの追加] ブレードのスクリーンショット](./media/app-protection-policies/app-protection-add-policy.png)

3. ポリシーの名前を指定して簡単な説明を追加し、ポリシーのプラットフォームの種類を選択します。 プラットフォームごとに複数のポリシーを作成できます。

4. **[アプリ]** を選択して **[アプリ]** ブレードを開くと、使用可能なアプリの一覧が表示されます。 一覧から、作成するポリシーに関連付けるアプリを 1 つまたは複数選択します。 ポリシーを作成するには、アプリを少なくとも 1 つ選択してください。  

5. アプリを選択したら、 **[選択]** を選び、選択内容を保存します。

6. **[ポリシーの追加]** ブレードで、 **[必要な設定の構成]** を選択して **[設定]** を開きます。

   ポリシー設定にはカテゴリが 3 つあります。
   - **データ保護** - このグループには、切り取り、コピー、貼り付け、名前を付けて保存の制限など、データ損失防止 (DLP) コントロールが含まれます。 これらの設定によって、アプリでユーザーがデータを操作する方法が決定されます。
   - **アクセス要件** - このグループには、エンド ユーザーが仕事でアプリにアクセスする方法を決定するアプリ別の PIN オプションが含まれます。  
   - **条件付き起動** - このグループには、最小 OS 設定、脱獄またはルート化されたデバイスの検出、オフライン猶予期間などの設定が含まれます。

   ユーザーが開始できるように、ポリシー設定には既定値が入力されています。 既定値が要件を満たす場合は、変更を加える必要はありません。

   > [!TIP]
   > これらのポリシー設定は、作業コンテキストでアプリを使用する場合にのみ適用されます。 エンド ユーザーが、個人のタスクを実行するためにアプリを使用する場合、これらのポリシーによる影響を受けることはありません。 作成した新しいファイルは、個人用ファイルだと見なされることに注意してください。 

7. **[OK]** を選択し、この構成を保存します。 これにより、 **[ポリシーの追加]** ブレードに戻ります。
8. **[作成]** を選択してポリシーを作成し、設定を保存します。

作成された新しいポリシーは、明示的にデプロイするまではいかなるユーザーにもデプロイされません。 ポリシーを展開するには、「[ユーザーへのポリシーの展開](app-protection-policies.md#deploy-a-policy-to-users)」を参照してください。

## <a name="deploy-a-policy-to-users"></a>ユーザーへのポリシーの展開

1. **[アプリ保護ポリシー]** ウィンドウでポリシーを選択します。

2. \* **[Intune App Protection]** ウィンドウで、 **[割り当て]** を選択し、 **[Intune App Protection - 割り当て]** ウィンドウを開きます。 *[含める]* タブで **[含めるグループを選択]** を選択します。 

   ![[割り当て] ウィンドウと [含めるグループを選択] メニュー オプションのスクリーンショット](./media/app-protection-policies/app-protection-policy-add-users.png)

3. **Azure Active Directory** にあるすべてのセキュリティ グループの一覧が表示されます。 このポリシーを適用するユーザー グループを選択し、 **[選択]** を選択します。 

    ![[ユーザー グループの追加] ウィンドウと Azure AD ユーザーの一覧のスクリーンショット](./media/app-protection-policies/azure-ad-user-group-list.png)

4. グループを含めたり除外したりした後で、 **[保存]** を選択して構成を保存し、ポリシーをユーザーにデプロイします。 構成を保存する前に **[破棄]** を選択すると、" *[含める]* " タブと " *[除外する]* " タブで行ったすべての変更内容が破棄されます。   
 
     ![[保存] オプションと [破棄] オプションが表示されるスクリーンショット](./media/app-protection-policies/save-assignment.png)
  
これで、作成したポリシーはユーザーに展開されました。

Microsoft Intune ライセンスが割り当てられているユーザーのみが、このポリシーの影響を受けます。 Intune ライセンスが割り当てられていない、選択したセキュリティ グループ内のユーザーは、影響を受けません。

>[!IMPORTANT]
> Intune を使用し、Configuration Manager によってデバイスを管理する場合、このポリシーは、選択したグループ直下のユーザーにのみ適用されます。 選択したグループ内で入れ子になっている子グループのメンバーは、影響を受けません。

エンド ユーザーは App Store または Google Play からアプリをダウンロードできます。 詳細については、次をご覧ください。
* [アプリ保護ポリシーを使用して Android アプリを管理するときの注意点](../fundamentals/end-user-mam-apps-android.md)
* [アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>既存のポリシーの変更
既存のポリシーを編集して、対象ユーザーに適用できます。 ただし、既存のポリシーを変更する場合、アプリに既にサインインしているユーザーには、8 時間にわたって変更が表示されません。

変更の効果をすぐに確認するには、エンド ユーザーはアプリからサインアウトし、もう一度サインインする必要があります。

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>ポリシーに関連付けられているアプリの一覧を変更するには

1. **[アプリ保護ポリシー]** ウィンドウで、変更するポリシーを選択します。

2. *[Intune App Protection]* ウィンドウで、 **[対象アプリ]** を選択してアプリの一覧を開きます。

3. 一覧でアプリを削除または追加し、 **[保存]** アイコンを選択して変更内容を保存します。

### <a name="to-change-the-list-of-user-groups"></a>ユーザー グループの一覧を変更するには


1. **[アプリ保護ポリシー]** ウィンドウで、変更するポリシーを選択します。

2. *[Intune App Protection]* ウィンドウで、 **[割り当て]** を選択して **[Intune App Protection - 割り当て]** ウィンドウを開きます。このウィンドウには、このポリシーを持つ現在のユーザー グループの一覧が表示されます。

3. ポリシーに新しいユーザー グループを追加するには、 *[含める]* タブで **[含めるグループを選択]** を選択し、ユーザー グループを選択します。 **[選択]** を選択してグループを追加します。 

4. ユーザー グループを除外するには、 *[除外]* タブで **[含めないグループを選択]** を選択し、ユーザー グループを選択します。 **[選択]** を選択してユーザー グループを削除します。  

5. 以前に追加されたグループを削除するには、" *[含める]* " タブまたは " *[除外する]* " タブのいずれかで、省略記号 (...) を選択し、 **[削除]** を選択します。 

5. 割り当てへの変更が準備できたら、 **[保存]** を選択して、構成を保存し、ポリシーを新しい一連のユーザーにデプロイします。 構成を保存する前に **[破棄]** を選択すると、" *[含める]* " タブと " *[除外する]* " タブで行ったすべての変更内容が破棄されます。

### <a name="to-change-policy-settings"></a>ポリシー設定を変更するには

1. **[アプリ保護ポリシー]** ウィンドウで、変更するポリシーを選択します。

2. *[Intune App Protection]* ウィンドウで、 **[プロパティ]** を選択し、編集可能な設定領域の一覧を開きます。 

3. **データ再配置**や**アクセス要件**など、設定を変更する設定領域を選択します。 次に、設定を新しい値に変更します。

4. **[保存]** アイコンを選択し、変更を保存します。 すべての変更が完了するまで、設定領域を変更し、修正し、変更を保存するプロセスを繰り返します。 完了後は *[Intune App Protection - プロパティ]* ウィンドウを閉じることができます。 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>デバイス管理状態に基づくアプリ保護ポリシーの対象指定
多くの組織では、企業所有デバイスなどの Intune モバイル デバイス管理 (MDM) マネージド デバイスと、Intune アプリ保護ポリシーでのみ保護されるアンマネージド デバイスの両方をエンド ユーザーが使用できるようにするのが一般的です。 多くの場合、アンマネージド デバイスは BYOD (Bring Your Own Devices/私物機器の業務利用) と呼ばれています。

Intune アプリ保護ポリシーの対象はユーザーの ID であるため、ユーザーの保護設定は登録されている (MDM 管理対象) デバイスと登録されていないデバイス (MDM なし) の両方に適用されます。 したがって、Intune に登録されている、または登録されていない iOS デバイスと Android デバイスを Intune アプリ保護ポリシーの対象にすることができます。 厳格なデータ損失防止 (DLP) 制御が行われているアンマネージド デバイスに対して 1 つの保護ポリシーを適用し、MDM マネージド デバイスに対して別の保護ポリシーを適用することができます。この場合、DLP 制御が少し緩和される可能性があります。 個人用の Android Enteprise デバイス上でこれがどのように動作するかを示した詳細ついては、[アプリ保護ポリシーと仕事用プロファイル](android-deployment-scenarios-app-protection-work-profiles.md)に関する記事を参照してください。

これらのポリシーを作成するには、Intune コンソールで **[クライアント アプリ]** 、 **[アプリ保護ポリシー]** の順に参照し、 **[ポリシーの作成]** を選択します。 既存のアプリ保護ポリシーを編集することもできます。 マネージド デバイスとアンマネージド デバイスの両方にアプリ保護ポリシーを適用するには、 **[すべてのアプリの種類を対象にする]** が **[はい]** (既定値) に設定されていることを確認してください。 管理状態に基づいて細かく割り当てる場合は、 **[すべてのアプリの種類を対象にする]** を **[いいえ]** に設定します。 

![[ポリシーの追加] ブレードと [すべてのアプリの種類を対象にする] のスクリーンショット](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>アプリの種類

- **[アンマネージド デバイス上のアプリ]** : アンマネージド デバイスとは、Intune MDM 管理が検出されなかったデバイスです。 これには、サードパーティの MDM ベンダーが含まれます。
- **[Intune マネージド デバイス上のアプリ]** :マネージド デバイスは、Intune MDM によって管理されます。
- **[Android 作業プロファイルでのアプリ]** : Android Enterprise 仕事用プロファイルのデバイスとして登録されているマネージド デバイス。

> Android デバイスでは、選択されているアプリの種類に関わらず、Intune ポータル サイト アプリのインストールが求められることに注意してください。 たとえば、[Intune マネージド デバイス上のアプリ] を選択した場合、アンマネージド Android デバイスがあるユーザーにも、まだメッセージが表示されます。

iOS の場合、アプリ保護ポリシー (APP) 設定のターゲットを Intune に登録されているデバイス上のアプリにするには、さらにアプリの構成設定が必要になります。

- **IntuneMAMUPN** を、MDM で管理されているすべてのアプリケーションに構成する必要があります。 詳細については、「[Microsoft Intune で iOS アプリ間のデータ転送を管理する方法](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm)」を参照してください。
- すべてのサードパーティ製アプリケーションと LOB MDM マネージド アプリケーションに **IntuneMAMDeviceID** を構成する必要があります。 **IntuneMAMDeviceID** を、デバイスの ID トークンに構成する必要があります。 たとえば、`key=IntuneMAMDeviceID, value={{deviceID}}` のように指定します。 詳細については、「[管理対象の iOS デバイス用アプリ構成ポリシーを追加する](app-configuration-policies-use-ios.md)」を参照してください。
- **IntuneMAMDeviceID** のみが構成されている場合、Intune APP はデバイスが管理対象であると見なしません。

> [!NOTE]
> デバイス管理状態に基づくアプリ保護ポリシーに関する特定の iOS サポート情報については、[管理の状態に基づいて対象とされる MAM 保護ポリシー](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-)に関するページを参照してください。

## <a name="policy-settings"></a>ポリシー設定
iOS と Android 用のポリシー設定の完全な一覧を表示するには、次のいずれかのリンクを選択します。

- [iOS ポリシー](app-protection-policy-settings-ios.md)
- [Android ポリシー](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>次の手順
[コンプライアンスとユーザーの状態を監視する](app-protection-policies-monitor.md)

## <a name="see-also"></a>関連項目
* [アプリ保護ポリシーを使用して Android アプリを管理するときの注意点](../fundamentals/end-user-mam-apps-android.md)
* [アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点](../fundamentals/end-user-mam-apps-ios.md)
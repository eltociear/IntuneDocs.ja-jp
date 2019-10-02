---
title: Microsoft Intune で MTD デバイスのコンプライアンス ポリシーを作成する
titleSuffix: Microsoft Intune
description: モバイル デバイスが会社のリソースにアクセスできるかどうかを決定するために、MTD パートナー脅威レベルを使用する Intune デバイスのコンプライアンス ポリシーを作成します。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2315136fe277f06f6dbb11c13139a9dc193ce6f7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722112"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Intune で Mobile Threat Defense (MTD) デバイス コンプライアンス ポリシーを作成する

> [!NOTE] 
> この情報は、すべての Mobile Threat Defense パートナーに適用されます。

Intune で MTD を使用すると、モバイル デバイス上で脅威を検出し、リスクを評価できます。 リスクを評価する Intune デバイス コンプライアンス ポリシー ルールを作成すれば、デバイスがポリシーに準拠しているかどうかを判断できます。 さらに、[条件付きアクセス ポリシー](create-conditional-access-intune.md)を使用することで、デバイスのコンプライアンスに基づいて、サービスへのアクセスを禁止できます。

## <a name="before-you-begin"></a>始める前に

MTD の設定の一部として、MTD パートナー コンソールで、さまざまな脅威を高、中、低として分類するポリシーを作成しておきます。 これにより、Intune デバイス コンプライアンス ポリシーに Mobile Threat Defense レベルを設定する必要があります。

MTD でのデバイス コンプライアンス ポリシーの前提条件:

- MTD と Intune の統合をセットアップする

## <a name="to-create-an-mtd-device-compliance-policy"></a>MTD デバイス コンプライアンス ポリシーを作成するには

1. [Azure Portal](https://portal.azure.com/) に移動し、Intune 資格情報でサインインします。

2. **Azure ダッシュボード**で、左側のメニューから **[すべてのサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。

3. **[Intune]** を選択すると、**Intune ダッシュボード**が開きます。

4. **Intune ダッシュ ボード**で、 **[デバイスのポリシー準拠]** を選択し、 **[管理]** セクションで **[ポリシー]** を選択します。

5. **[Create policy]\(ポリシーの作成\)** を選択し、デバイス コンプライアンスの **[名前]** 、 **[説明]** を入力し、 **[プラットフォーム]** を選択してから **[設定]** セクションの **[構成]** を選択します。

6. **[コンプライアンス ポリシー]** ウィンドウで、 **[デバイスのヘルス]** を選択します。

7. **[デバイスのヘルス]** ウィンドウの、 **[デバイスは、デバイス脅威レベル以下であることが必要]** の下でモバイル脅威レベルをドロップダウン リストから選択します。

    」を参照します。  **[セキュリティ保護]** :このレベルはセキュリティ上最も安全です。 デバイスにいかなる脅威も存在できず、デバイスからは引き続き会社のリソースにアクセスできます。 いずれかの脅威が見つかった場合、デバイスは非準拠と評価されます。

    b.  **[低]** :存在する脅威が低レベルの場合のみ、デバイスは準拠しています。 低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。

    c.  **[中]** :デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠しています。 高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。

    d.  **[高]** :このレベルは最も安全性の低い状態です。 この場合、すべての脅威レベルが許可され、レポート目的のみで Mobile Threat Defense が使用されます。 デバイスには、この設定でアクティブ化された MTD アプリが含まれている必要があります。

8. **[OK]** を 2 回クリックしてから、 **[作成]** を選択します。

> [!IMPORTANT]
> Office 365 またはその他のサービスに対する条件付きアクセス ポリシーを作成すると、デバイス コンプライアンス評価が適用され、非準拠デバイスはデバイスで脅威が解決されるまで会社のリソースへのアクセスは禁止されます。

## <a name="to-assign-an-mtd-device-compliance-policy"></a>MTD デバイス コンプライアンス ポリシーを割り当てるには

デバイス コンプライアンス ポリシーをユーザーに割り当てるには、前に構成したポリシーを選択します。 既存のポリシーは、 **[デバイスのポリシー準拠 - ポリシー]** ウィンドウで確認できます。

1. ユーザーに割り当てるポリシーを選択し、 **[割り当て]** を選択します。 この操作でウィンドウが表示され、 **[Azure Active Directory セキュリティ グループ]** を選択してポリシーに割り当てることができます。

2. **[Select groups to include]\(含めるグループの選択\)** を選択すると、Azure AD セキュリティ グループが表示されたウィンドウが開きます。  **[選択]** を選択すると、ポリシーがユーザーに展開されます。

    > [!NOTE] 
    > ポリシーがユーザーに適用されました。 ポリシーの対象となっているユーザーが使用しているデバイスは、コンプライアンスが評価されます。

## <a name="next-steps"></a>次の手順

- [Intune で MTD を有効にする](mtd-connector-enable.md)
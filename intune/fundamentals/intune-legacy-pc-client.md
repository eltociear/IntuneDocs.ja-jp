---
title: レガシ Intune PC クライアントと Azure 上の Intune
description: Azure で Intune を使用して、組織の Windows デバイスを管理する際の考慮事項です。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.assetid: 1f104923-12df-453c-9c20-942ef65a0945
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ab1be3d34d52e824d1ff06124e28206fb7b07a1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72510189"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Azure コンソールと従来の Intune PC クライアントでの Intune

Intune は、Azure ベースの SaaS アプリケーション サービス アーキテクチャを使用しています。 Azure はスケール、容量、およびパフォーマンスの面で大幅に改善されています。 これにより、Intune の管理エクスペリエンスが強化され、Azure portal のワークフローが最適化されています。 

Azure で Intune を使用して組織の Windows デバイスを管理する場合、次の点を考慮してください。

## <a name="manage-windows-10-devices-by-using-mdm"></a>MDM を使用した Windows 10 デバイスの管理

従来の Intune PC クライアントを使用する代わりに、[Windows 10 デバイスを管理するモバイル デバイス管理 (MDM)](../configuration/device-restrictions-windows-10.md) を使用することをお勧めします。 MDM を使用した Windows 10 デバイスの管理機能は、Azure Portal 上の Intune で提供されています。 Windows 10 の MDM には、従来の Intune PC クライアントでは提供されていない、多くの新しい管理およびセキュリティ機能があります。

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>従来の PC クライアント機能が使用できるのは Silverlight コンソールのみです。

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune PC クライアント管理ワークフローでは [Silverlight ベースの Intune 管理コンソール](https://manage.microsoft.com/)が使用されており、次のような影響があります。

- Intune PC クライアントを使用する非グループ化管理タスクのすべてで Silverlight コンソールを使用する必要があります。
- グループを管理する場合、[Azure Portal で Intune](https://portal.azure.com/) を使用する必要があります。 Intune では従来の Intune グループの代わりに Azure AD グループを使用するようになったため、この要件が存在します。 

Azure AD グループへの切り替えのために、Silverlight コンソール ダッシュボード ビューで "グループ ベース" のフィルター処理が若干変わりました。 更新された Silverlight UI でフィルター処理を行うには、次の手順に従います。

1. ビューを選択します。
2. **[フィルター]** ボックスで、フィルター処理の基準となるグループの名前を入力して Enter キーを押します。 これにより、リスト ビューがその特定グループ内のデバイスにフィルターされます。

   ![選択されていないドロップダウン入力をフィルター処理します](./media/intune-legacy-pc-client/image01.png)


## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Intune PC クライアントを使用した Windows 7 の管理の継続

MDM を使用して管理できない Windows 7 では、Silverlight コンソールのみで、既存の Intune PC クライアント機能のサポートが継続されます。 Windows 10 にアップグレードする場合、MDM 管理への移行を検討してください。

## <a name="mdm-capabilities"></a>MDM の機能

PC クライアントと MDM 機能の詳細な比較については、[Windows PC をコンピューターやモバイル デバイスとして管理する場合の比較](pc-management-comparison.md)に関するページをご覧ください。 MDM の更新プログラムにより、MDM に登録されている Windows 10 デバイスに、Win 32 アプリ用のオプションの評価を含む新しい管理機能が引き続き組み込まれます。 サービスへの最新リリースの追加については、「[新機能](whats-new.md)」をご覧ください。

## <a name="switch-from-pc-client-to-mdm"></a>PC クライアントから MDM への切り替え

Intune PC クライアントでの Windows 10 デバイス管理から MDM での管理に切り替えるには、次の手順に従います。

1. Silverlight コンソールで、**選択的ワイプ**を実行して PC クライアントからデバイスを登録解除します。
  [デバイスを選択的にワイプする] オプションボタンがオンになっている ![警告ポップアップ](./media/intune-legacy-pc-client/image02.png)
2. [MDM (および/または Azure AD Join)](../enrollment/windows-enroll.md) を使用してデバイスを再登録します。

## <a name="next-steps"></a>次の手順
[Windows デバイスの登録](../enrollment/windows-enroll.md)

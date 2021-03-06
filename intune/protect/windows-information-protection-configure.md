---
title: Microsoft Intune での Windows Information Protection 設定
titleSuffix: Microsoft Intune
description: Windows 情報保護の管理に使用できる Microsoft Intune の設定について説明します。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f4c8f30359869761482e55680c9d935722bdf67
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508744"
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Microsoft Intune で Windows Information Protection を構成する方法

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

企業内に従業員所有デバイスが増加するのに従い、企業のコントロールが届かない電子メール、ソーシャル メディア、パブリック クラウドなどのアプリやサービスを介して偶発的にデータが漏えいするリスクも増大しています。 たとえば、従業員が個人用の電子メール アカウントから最新のエンジニアリング画像を送信したり、製品情報をコピーしてツイートに貼り付けたり、作成中の営業レポートをパブリック クラウドの記憶域に保存したりするときなどです。

**Windows 情報保護**は、この潜在的なデータ漏えいの防止に役立ちます。それ以外の場合は従業員のエクスペリエンスを妨げることはありません。 また、企業が所有するデバイスと従業員が作業のために持ち込む個人用デバイスでもエンタープライズ アプリとデータを偶発的なデータ漏えいから保護します。既存の環境や他のアプリを変更する必要はありません。

この Intune ポリシーは、Windows 情報保護によって保護されているアプリ、エンタープライズ ネットワークの場所、保護レベル、および暗号化設定の一覧を管理します。

>[!NOTE]
> Windows 10 ポータル サイト アプリを Windows Information Protection とともに使用するには、ポータル サイト アプリを Windows Information Protection モードの**除外対象**に追加する必要があります。 

詳細については、次をご覧ください。
- [Windows 情報保護 (WIP) を使用した企業データの保護](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)
- [従来の Microsoft Intune コンソールを使用して Windows 情報保護 (WIP) ポリシーを作成する](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Azure Portal での Microsoft Intune を使用して MDM で Windows 情報保護 (WIP) ポリシーを作成する](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Azure Portal での Microsoft Intune を使用して MAM で Windows 情報保護 (WIP) ポリシーを作成する](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)

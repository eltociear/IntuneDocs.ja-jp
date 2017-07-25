---
title: "デバイス コンプライアンスを監視する方法"
titleSuffix: Intune on Azure
description: "デバイス コンプライアンスを監視する方法を説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f18bfa7fb045dbad4ab785c2c8e1bc13fc439db
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-monitor-device-compliance-in-intune"></a>Intune でデバイス コンプライアンスを監視する方法

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**[概要]** ブレードでは、**コンプライアンス プロファイル**の状態の概要を確認できます。
対話形式でグラフをクリックスルーして、詳細にドリルダウンできます。 複数のコンプライアンス プロファイルを構成している場合は、ポリシー ブレードに移動し、**[管理]** セクションで **[レポート]** を選択して、各ポリシーの状態を表示することもできます。  表示できるレポートの詳細を以下に示します。

##  <a name="device-compliance"></a>デバイスのポリシー準拠

デバイス コンプライアンス レポートの概要ビューには、次のいずれかとして報告されたデバイスの数に関する集計情報がまず表示されます。

- **[準拠]**: デバイスは最近コンプライアンスが評価され、指定したコンプライアンス プロファイル設定に準拠していると判断されました。
- **[非準拠]**: デバイスは評価され、非準拠と判断されました。  プロファイルで猶予期間が指定されていた場合、猶予期間が終了して、デバイスが非準拠状態になっています。
- **[猶予期間]**: デバイスは評価され、非準拠と判断されました。 ただし、デバイスが実際に非準拠としてマークされるまでの猶予期間がまだ適用されています。

各セクションにドリルダウンすると、個々のデバイスとユーザーの詳細を表示できます。

## <a name="setting-compliance"></a>コンプライアンスの設定

コンプライアンスの設定レポートには、次のような各コンプライアンス設定の詳細が表示されます。

- 設定に準拠していないデバイスの数。
- 設定が適用されているプラットフォーム。

各設定をドリルダウンすると、これらの設定が有効になっているプロファイルの詳細情報と設定の値を表示できます。
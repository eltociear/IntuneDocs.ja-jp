---
title: "コンプライアンス ポリシーでデバイスの防御ルールを有効にする | Microsoft Intune"
description: "デバイスのコンプライアンス ポリシーでモバイル脅威防御ルールを有効にします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: efddf7645d0548c842ae8aa3b1ca5222023913b5


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>コンプライアンス ポリシーでデバイスの脅威防御ルールを有効にする
Intune と Lookout Mobile Threat Protection を使用すると、デバイスのモバイル脅威を検出してリスク評価を行うことができます。 リスク評価を含むコンプライアンス ポリシー ルールを作成すると、デバイスがポリシーに準拠しているかどうかを判断できます。 条件付きアクセス ポリシーを使用すると、デバイスのコンプライアンスに基づいて、Exchange、SharePoint、またはその他のサービスへのアクセスを許可または禁止できます。

Lookout デバイス脅威防御をデバイスのコンプライアンス ポリシーに反映するには:

* コンプライアンス ポリシーで **[Device Threat Protection]** (デバイス脅威防御) ルールが有効になっている必要があります。

* **Intune 管理者コンソール**の **[Lookout Status]** (Lookout の状態) ページで、**[Active]** (有効) と表示される必要があります。 Lookout の統合を有効にする方法の詳細については、「[Intune 管理者コンソールで Lookout MTP の接続を有効にする](enable-lookout-mtp-connection-in-intune.md)」をご覧ください。


コンプライアンス ポリシーでデバイス脅威防御ルールを作成する前に、[Lookout デバイス脅威保護用にサブスクリプションを設定](set-up-your-subscription-with-lookout-mtp.md)し、[Intune で Lookout の接続を有効](enable-lookout-mtp-connection-in-intune.md)にし、[Lookout for Work アプリを構成](configure-and-deploy-lookout-for-work-apps.md)することをお勧めします。 コンプライアンス ルールは、セットアップが完了した後でのみ適用されます。

デバイスの脅威防御ルールを有効にするには、既存のコンプライアンス ポリシーを使うか、または新しいコンプライアンス ポリシーを作成します。

Lookout デバイス脅威保護をセットアップするときに、[Lookout コンソール](https://aad.lookout.com)で、さまざまな脅威を高、中、低のレベルに分類するポリシーを作成しました。 Intune のコンプライアンス ポリシーでは、脅威レベルを使用して許容される最大脅威レベルを設定します。

**Intune 管理者コンソール**の**コンプライアンス ポリシー** ページで、**[デバイスのヘルス]** に移動し、トグル オプションを使用して **[Device Threat Protection]** (デバイス脅威防御) ルールを有効にします。 次に、最大許容脅威レベルとして次のいずれかを選択します。
* **[None (secured)]** (なし (セキュリティ保護あり)): これはセキュリティ上最も安全です。  デバイスにはいかなる脅威も存在できないことを意味します。  いずれかのレベルの脅威が見つかった場合、デバイスは非準拠と評価されます。  
* **[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。 それより高い脅威が存在する場合、デバイスは非準拠状態になります。
* **[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。 高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。
* **[High]** (高): 最も安全性の低い状態です。 基本的にすべての脅威レベルが許容されるため、通常、このソリューションはレポートを目的とした場合にのみ役に立ちます。

![デバイス脅威防御ルールの設定を示すスクリーンショット ](../media/mtp/mtp-compliance-policy-rule.png)

![デバイス脅威防御ルール設定の脅威レベル オプションを示すスクリーンショット](../media/mtp/mtp-compliance-policy-setting.png)

Office 365 およびその他のサービスに対する条件付きアクセス ポリシーでは、上記のコンプライアンス評価が考慮され、非準拠デバイスは脅威が解決されるまで会社のリソースへのアクセスは禁止されます。

デバイスのコンプライアンスの状態は、**Intune 管理者コンソール**の **[すべてのデバイス]** ページで確認できます。

![デバイスのコンプライアンス状態が表示されている Intune 管理者コンソールのデバイス ページのスクリーンショット](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>次のステップ
* 条件付きアクセス ポリシーを作成します
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


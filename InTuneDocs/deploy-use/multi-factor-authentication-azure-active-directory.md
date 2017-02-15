---
title: "Azure AD を使用する多要素認証 | Microsoft Docs"
description: "デバイス登録で Azure AD の多要素認証を要求する方法。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
translationtype: Human Translation
ms.sourcegitcommit: 85462d6cb5e3dc6ce8e94fe8fd1bc1c1c2b6e4f3
ms.openlocfilehash: 6e20eca60886781ae884107a224245639c5f107c


---

# <a name="multi-factor-authentication-for-microsoft-intune"></a>Microsoft Intune の多要素認証

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune には、デバイス登録用に Azure AD の多要素認証 (MFA) 機能が統合されていて、会社のリソースのセキュリティ保護に利用できます。 MFA には、ユーザー名とパスワードだけでなくテキスト認証などの認証の要素が必要です。 iOS、Android、Windows 8.1 以上、または Windows Phone 8.1 以上のデバイスでサポートされています。

> [!NOTE]
>
> これは、Intune での MFA の新しいエクスペリエンスです。 移行前の古いエクスペリエンスについては、「[Protect Windows devices with multi-factor authentication](protect-windows-devices-with-multi-factor-authentication.md)」で説明されています。
>
> 以前のバージョンの Configuration Manager (リリース 1610 より前) では、Configuration Manager 管理コンソールに MFA の設定が表示されますが、 Configuration Manager 管理コンソールで MFA を構成しようとしないでください。MFA は機能しません。 MFA はこのトピックの説明に従って構成してください。

### <a name="configuring-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>デバイス登録時に多要素認証を要求する Intune の構成
デバイス登録時に MFA を要求するには、次の手順に従います。

1. 管理者資格情報で [Microsoft Azure ポータル](https://manage.windowsazure.com)にサインインします。
2. テナントを選択します。
2. **[アプリケーション]** タブを選択します。 Azure AD のセキュリティ機能を構成できるサービスの一覧が表示されます。
3. **[Microsoft Intune enrollment (Microsoft Intune 登録)]** を選択します。
4. **[構成]** を選択します。 
5. **[多要素認証と場所ベースのアクセス規則]** では、次の操作をすることができます。
    
    -  アクセス規則の有効化
    -  すべてのユーザーまたは特定の Azure セキュリティ グループのどちらに規則を適用するか選択します。
    -  すべてのデバイスの登録では、多要素認証を要求します。
    -  デバイスが動作していないときの登録では、多要素認証を要求します。
    -  **[Block access to corporate resources (会社のリソースへのアクセスをブロックする)]** を選択して、デバイスが企業ネットワークに接続されていないときはデバイスを登録できないようにします。 
4. **社内ネットワークの場所の定義/編集**へのリンクをクリックして、デバイス登録のネットワーク接続要件を構成することもできます。

> [!IMPORTANT]
> 
> [Microsoft Intune enrollment (Microsoft Intune 登録)] の **[デバイス ベースのアクセス規則]** は構成しないでください。



<!--HONumber=Dec16_HO3-->


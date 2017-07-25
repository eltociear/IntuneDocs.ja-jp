---
title: "Intune ポリシーによる Samsung KNOX 用アプリの許可/禁止"
titleSuffix: Intune on Azure
description: "カスタム プロファイルを作成して、Samsung KNOX Standard デバイス用のアプリを許可またはブロックします。\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8245bb3fa8f08e719df903a70f079f4fdf534ca5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2017
---
<a id="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune" class="xliff"></a>
# Microsoft Intune でカスタム ポリシーを使用して Samsung KNOX Standard デバイス用のアプリを許可またはブロックする
[!INCLUDE[azure_portal](./includes/azure_portal.md)] 次のいずれかを作成する Microsoft Intune のカスタム ポリシーを作成するには、このトピックの手順を使用します。

- デバイスでの実行をブロックするアプリの一覧。 この一覧のアプリは、ポリシー適用時に既にインストールされていた場合でも、実行をブロックされます。
- デバイスのユーザーが Google Play ストアからインストールできるアプリの一覧。 一覧のアプリのみをインストールできます。 他のアプリはストアからインストールできません。

これらの設定は、Samsung KNOX Standard を実行するデバイスでのみ使用できます。

<a id="create-an-allowed-or-blocked-app-list" class="xliff"></a>
## 許可されているアプリまたはブロックされているアプリの一覧の作成

1. Azure ポータルにサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス構成]** を選択します。
2. **[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。
2. プロファイルの一覧ブレードで、**[プロファイルを作成します]** を選択します。
3. **[プロファイルを作成します]** ブレードで、デバイス プロファイルの**名前**と省略可能な**説明**を入力します。
2. **[プラットフォームの種類]** では **[Android]** を、[プロファイルの種類] では **[カスタム]** を選択します。
3. **[設定]** をクリックします。
3. **[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。
4. **[OMA-URI 設定の追加または編集]** ダイアログ ボックスで、以下を指定します。

<a id="for-a-list-of-apps-that-are-blocked-from-running-on-the-device" class="xliff"></a>
### デバイスでの実行がブロックされているアプリの一覧の場合:

- **[名前]** - 「**PreventStartPackages**」と入力します。
- **[説明]** - "実行されないようにブロックされているアプリの一覧" のような説明 (省略可能) を入力します。
-   **[データ型]** - ドロップダウン リストで **[文字列]** を選択します。
-   **[OMA-URI]** - 「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**」と入力します
-   **[値]** - ブロックするアプリ パッケージ名の一覧を入力します。 区切り記号としては、**; : ,** **|** を使用できます。 (例: package1;package2;)

<a id="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps" class="xliff"></a>
### 他のすべてのアプリの実行中にユーザーが Google Play ストアからインストールできるアプリの一覧の場合:
- **[名前]** - 「**AllowInstallPackages**」と入力します。
- **[説明]**: "ユーザーが Google Play からインストールできるアプリの一覧" のような説明 (省略可能) を入力します。
- **[データ型]** - ドロップダウン リストで **[文字列]** を選択します。
- **[OMA-URI]** - 「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**」と入力します
- **[値]** - 許可するアプリ パッケージ名の一覧を入力します。 区切り記号としては、**; : ,** **|** を使用できます。 (例: package1;package2;)

4. **[OK]** をクリックし、**[プロファイルを作成します]** ブレードで **[作成]** を選択します。

>[!TIP]
> Google Play ストアでアプリを参照して、アプリのパッケージ ID を確認できます。 パッケージ ID は、アプリのページの URL に含まれます。 たとえば、Microsoft Word アプリのパッケージ ID は **com.microsoft.office.word** です。

各対象デバイスの次のチェックイン時に、アプリの設定が適用されます。


<!---## Assign the custom profile--->
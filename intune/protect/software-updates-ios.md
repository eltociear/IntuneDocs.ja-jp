---
title: Microsoft Intune - Azure での iOS ソフトウェア更新ポリシーの構成 | Microsoft Docs
description: Microsoft Intune で、ソフトウェア更新プログラムが Intune によって管理または監視される iOS デバイス上に自動的にインストールされるときに、制限する構成ポリシーを作成または追加します。 更新プログラムがインストールされていない日付と時刻を選択できます。 また、このポリシーをグループ、ユーザー、またはデバイスに割り当て、任意のインストール エラーを確認することもできます。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54e6cc0b3df95c74abf4b4ef1b827f8e121e3645
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726662"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Intune に iOS ソフトウェア更新プログラム ポリシーを追加する

ソフトウェアの更新ポリシーにより、監視対象の iOS デバイスに利用可能な最新の OS 更新プログラムを強制的に自動インストールします。 ポリシーを構成しているときに、デバイスで更新プログラムをインストールしない日時を追加できます。

この機能は、以下に適用されます。

- iOS 10.3 以降 (監督下)

デバイスは約 8 時間ごとに Intune でチェックインされます。 更新プログラムを利用できて、制限時間中ではない場合、デバイスで最新の OS 更新プログラムをダウンロードしてインストールします。 デバイスを更新するために必要なユーザーの操作はありません。 ポリシーにより、ユーザーが手動で OS を更新できなくなることはありません。

## <a name="configure-the-policy"></a>ポリシーの構成

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) にサインインします。
2. **[ソフトウェア更新プログラム]**  >  **[iOS のポリシーを更新する]**  >  **[作成]** を選択します。
3. 次の設定を入力します。

    - **名前**: ソフトウェア更新プログラム ポリシーの名前を入力します。 たとえば、「`iOS restricted update times`」と入力します。
    - **説明**:ポリシーの説明を入力します。 この設定は省略可能ですが、推奨されます。

4. **[設定]、[構成]** の順に選択します。 次の設定を入力します。

    - **更新プログラムのインストールを実行しない時間を選択**:更新プログラムを強制的にインストールしない制限付き時間枠を指定します。
      - 夜通しのブロックはサポートされておらず、また、機能しない可能性があります。 たとえば、*開始時刻*が午後 8 時で*終了時刻*が午前 6 時のポリシーを設定しないでください。
      - 午前 12 時に開始し、午前 12 時に終了するポリシーは 24 時間ではなく 0 時間として見なされ、結果的に制限なしとなります。

      時間枠を制限付きで設定するとき、次の詳細を入力します。

      - **曜日**:更新プログラムがインストールされていない曜日を選択します。 たとえば、月、水、金にチェックを入れると、月、水、金は更新プログラムがインストールされません。
      - **タイム ゾーン**:時間帯を選択します。
      - **開始時刻**:制限付き時間枠の開始時刻を選択します。 たとえば、午前 5 時と入力すると、更新プログラムは午前 5 時からインストールされません。
      - **終了時刻**:制限付き時間枠の終了時刻を選択します。 たとえば、午前 1 時と入力すると、更新プログラムは午前 1 時からインストールできます。

    - **ソフトウェア更新プログラムがエンド ユーザーに表示されるまでの遅延日数 (スケジュールされた更新は変更されない)** : 

      ** 監視対象の iOS デバイスで特定の時間だけソフトウェア更新プログラムの表示を遅らせる場合は、[[デバイスの制限]](../configuration/device-restrictions-ios.md#general) でそれらの設定を構成します。 ソフトウェア更新ポリシーによって、デバイスの制限が上書きされます。 両方を設定した場合、毎回、ソフトウェア更新ポリシーが優先されます。

      > [!IMPORTANT]  
      > *開始時刻*と*終了時刻*が午前 12 時になっているポリシーは、24 時間ではなく、0 時間として見なされます。 結果的に制限なしとなります。  

5. **[OK]** 、 **[作成]** の順に選択し、変更を保存し、ポリシーを作成します。

プロファイルが作成され、ポリシー一覧に表示されます。

Intune サポート チームからのガイダンスについては、「[Delay visibility of software updates in Intune for supervised devices](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753)」 (監視されているデバイスについて、Intune にソフトウェア更新プログラムの遅延を表示する) を参照してください。

> [!NOTE]
> Apple MDM では、デバイスで特定の時刻または日付によって強制的に更新プログラムをインストールすることはできません。

## <a name="change-the-restricted-times-for-the-policy"></a>ポリシーを制限する時間の変更

1. **[ソフトウェア更新プログラム]** で **[iOS のポリシーを更新する]** を選択します。
2. 既存のポリシー、 **[プロパティ]** の順に選択します。
3. 制限時間を更新します。

    1. 曜日を選択します。
    2. このポリシーが適用されるタイム ゾーンを選択します。
    3. ブラックリストにある時間の開始時刻と終了時刻を入力します。

    > [!NOTE]
    > **開始時刻**と**終了時刻**の両方が午前 12 時に設定されている場合、Intune では、更新プログラムのインストールのタイミングに関する制限が確認されません。 つまり、 **[更新プログラムのインストールを実行しない時間を選択]** に設定した構成は無視され、更新プログラムはいつでもインストールできます。  

## <a name="assign-the-policy-to-users"></a>ポリシーをユーザーに割り当てる

既存のポリシーは、グループ、ユーザー、またはデバイスに割り当てられます。 割り当てられたときに、ポリシーが適用されます。

1. **[ソフトウェア更新プログラム]** で **[iOS のポリシーを更新する]** を選択します。
2. 既存のポリシー、 **[割り当て]** の順に選択します。
3. Azure Active Directory のグループ、ユーザー、またはデバイスを選択して、このポリシーに含めるか、このポリシーから除外します。
4. **[保存]** を選び、グループにポリシーを展開します。

ポリシーの対象となっているユーザーが使用しているデバイスは、Update Compliance で評価されます。 このポリシーでは、ユーザーレス デバイスもサポートされます。

## <a name="monitor-device-installation-failures"></a>デバイスのインストール エラーを監視する
<!-- 1352223 -->
**[ソフトウェア更新プログラム]** の **[Installation failures for iOS devices]\(iOS デバイスのインストール エラー\)** では、更新ポリシーの対象、更新が試みられた監視対象の iOS デバイス、更新できなかった iOS デバイスの一覧が表示されます。 デバイスごとに、デバイスが自動的に更新されない理由のステータスを確認できます。 リストには、正常な最新デバイスは表示されません。 "最新" のデバイスには、デバイス自体でサポートできる最新の更新プログラムが含まれています。

## <a name="next-steps"></a>次の手順

[プロファイルを割り当て](../configuration/device-profile-assign.md)、[その状態を監視](../configuration/device-profile-monitor.md)します。
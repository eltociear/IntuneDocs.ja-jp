---
title: 展開の目標、目的、課題を判別する
titleSuffix: Microsoft Intune
description: この記事は、Microsoft Intune のクラウド専用実装における展開の目標、目的、課題の判別に役立ちます。
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ea88396c9637b0eaf8fa6886f33164fafe25b09
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509959"
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>展開の目標、目的、課題を判別する

適切な展開を計画するには、潜在的な課題と共に、組織の展開の目標および目的を特定することから始まります。 それぞれの領域について詳しく説明します。

## <a name="deployment-goals"></a>展開の目標

展開の目標は、組織に Intune を展開することで得られるであろう長期的な実績です。 次の一覧では、そのような目標の例と、目標の説明およびビジネス価値を示します。

- **Office 365 と統合し、Office モバイル アプリの使用をサポートする**

  - **説明:** Office 365 との緊密な統合、およびアプリ保護付きの Office モバイル アプリの使用を提供します。

  - **ビジネス価値:** ユーザーが使い慣れた好みのアプリの使用を許可して、セキュリティで保護し、ユーザー エクスペリエンスを向上させます。

- **モバイル デバイスで社内サービスへのアクセスを有効にする**

  - **説明:** 従業員が必要に応じてどこからでも、最も適切なデバイスを使用して、生産性を向上できるようにします。 このプロジェクトは、安全な方法でモバイルの生産性と企業データへのアクセスを可能にする必要があります。

  - **ビジネス価値:** 従業員が必要な場所から機敏に作業でき、ビジネスの競争力を高め、満足感のある作業環境を提供します。

- **モバイル デバイスのデータ保護を提供する**

  - **説明:** データがモバイル デバイスに保存されている場合、悪意による損失や偶発的な損失または共有から保護する必要があります。

  - **ビジネス価値:** データ保護では、確実に競争力を維持し、クライアントおよびクライアントのデータを最大限の努力を払って扱うことが不可欠です。

- **コストの削減**

  - **説明:** 可能な場合、プロジェクトでは展開コストおよび運用コストを削減します。

  - **ビジネス価値:** リソースを効率的に使用すると、ビジネスでの他の領域での投資、競争力の効率化、およびクライアントへの適切なサービスの提供を可能にします。

## <a name="deployment-objectives"></a>展開の目的

展開の目的は、組織が Intune 展開の目標を達成するために行う具体的な行動です。 次の一覧では、展開の目的の例と、その目的の達成方法を示します。

- **デバイス管理ソリューションの数を減らす**

  - **実装:** 単一のモバイル デバイス管理ソリューションへの集約: アプリおよびデバイスの企業データ保護のための Microsoft Intune。

- **セキュリティで保護された、Exchange および SharePoint Online へのアクセスを提供する**

  - **実装:** Exchange および SharePoint Online に条件付きアクセスを適用します。

- **企業データがモバイル デバイスで社外サービスに格納または転送されないようにする**

  - **実装:** Microsoft Office および基幹業務アプリに Intune アプリ保護ポリシーを適用します。

- **デバイスからの企業データのワイプ機能を提供する**

  - **実装:** Intune にデバイスを登録します。 これにより、適切なタイミングで企業のデータやリソースをリモート ワイプできるようになります。

## <a name="deployment-challenges"></a>展開の課題

展開の課題は、組織が最も関心を寄せる問題で、それにより展開に悪影響が及ぶ可能性があります。 課題は、以前のプロジェクトで発生した、回避すべき過去の問題に関連していることもあれば、現在の展開での取り組みに関する新しい問題に関連していることもあります。 次の一覧では、Intune 展開の課題の例と、可能性のある対策を示します。

- サポートの準備やエンド ユーザー エクスペリエンスは、最初のプロジェクト スコープには含まれません。 このため、エンド ユーザーに採用されにくいといった問題やサポート組織の課題が生じています。

  - **対策:** サポート トレーニングを組み込みます。 展開計画で定めた成功の指標を使用して、エンド ユーザー エクスペリエンスを検証します。

- 目標や成功の指標が明確に定義されていないため、成果が目に見えません。 問題が発生した場合、組織の対応が後手に回る可能性もあります。

  - **対策:** プロジェクト スコープの早い段階で目標と成功の判断基準を定義し、それらのデータ ポイントを利用し、他のロールアウト フェーズを具体化します。 目標は SMART (Specific (具体的な)、Measurable (測定可能な)、Attainable (達成可能な)、Realistic (現実的な)、Timely (時宜にかなった)) ものになるように設定します。 ロールアウト計画が順調に進行するように各フェーズの目標に合わせて指標を設定します。

- 組織の理解を得られるような明瞭な価値提案を作成し、その正当性を立証し、積極的に伝える努力を怠ると、 多くの場合、導入が制限され、十分な投資収益率 (ROI) が得られません。

  - **対策:** プロジェクトにあわてて取りかからず、目標と目的が明確に定義されていることを確認します。 新機能の認知やトレーニングにはこれらの目標や目的を取り入れ、Intune を組織が選択した理由をユーザーに理解してもらいます。

## <a name="next-steps"></a>次の手順

これで、展開の目標、目的、および潜在的な課題を識別しました。次のセクションに移動しましょう: [Intune ユース ケース シナリオの特定](planning-guide-scenarios.md)

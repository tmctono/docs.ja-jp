---
title: コード分析の破壊的変更
description: .NET ソース コード アナライザーの破壊的変更の一覧を示します。
ms.date: 09/02/2020
ms.openlocfilehash: 3cbe2ecf5d08084db542db0c2da016f1f391452e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538925"
---
# <a name="code-analysis-breaking-changes"></a>コード分析の破壊的変更

このページでは、次の破壊的変更について説明します。

| 互換性に影響する変更点 | 導入されたバージョン |
| - | :-: |
| [CA1416:プラットフォームの互換性](#ca1416-platform-compatibility) | 5.0 |
| [CA1417:P/Invoke 用の文字列パラメーターの OutAttribute](#ca1417-outattribute-on-string-parameter-for-pinvoke) | 5.0 |
| [CA1831: 文字列に範囲ベースのインデクサーの代わりに AsSpan を使用します](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | 5.0 |
| [CA2013: 値の型と共に ReferenceEquals を使用しないでください](#ca2013-do-not-use-referenceequals-with-value-types) | 5.0 |
| [CA2014: stackalloc はループ内で使用しないでください。](#ca2014-do-not-use-stackalloc-in-loops) | 5.0 |
| [CA2015: MemoryManager から派生した型にはファイナライザーを定義しません\<T>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | 5.0 |
| [CA2200:スタック詳細を保持するために再度スローします](#ca2200-rethrow-to-preserve-stack-details) | 5.0 |
| [CA2247: TaskCompletionSource コンストラクターの引数は、TaskCreationOptions 値にする必要があります](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ca2200-rethrow-to-preserve-stack-details](../../../includes/core-changes/codeanalysis/5.0/ca2200-rethrow-to-preserve-stack-details.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***

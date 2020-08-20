---
title: 相互運用性の破壊的変更
description: .NET Core と .NET 5.0 以降の相互運用性における破壊的変更を一覧で示します。
ms.date: 06/23/2020
ms.openlocfilehash: bac60631f8515eaf102f9d6e75fe817baceb7824
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062426"
---
# <a name="interop-breaking-changes"></a>相互運用性の破壊的変更

このページでは、次の破壊的変更について説明します。

| 互換性に影響する変更点 | 導入されたバージョン |
| - | :-: |
| [Windows 以外のプラットフォームでは A/W サフィックスのプローブは行われません](#no-aw-suffix-probing-on-non-windows-platforms) | 5.0 |
| [WinRT の組み込みサポートは .NET から削除されています](#built-in-support-for-winrt-is-removed-from-net) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***

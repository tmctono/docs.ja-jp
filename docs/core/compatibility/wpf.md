---
title: WPF 破壊的変更
description: .NET Core および .NET 5 の Windows Presentation Framework における破壊的変更の一覧を示します。
ms.date: 09/08/2020
ms.openlocfilehash: 3bd5cb585509118fbc3ca9ca08c6ed15b4853b93
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679306"
---
# <a name="breaking-changes-in-windows-presentation-framework-wpf"></a>Windows Presentation Foundation (WPF) の破壊的変更

WPF のサポートは、.NET Core にバージョン 3.0 で追加されました。 この記事では、WPF の破壊的変更を、導入された .NET のバージョン別に説明します。 この記事は、.NET Framework または以前のバージョンの .NET Core (3.0 以降) から WPF アプリをアップグレードするユーザーを対象としています。

このページでは、次の破壊的変更について説明します。

| 互換性に影響する変更点 | 導入されたバージョン |
| - | :-: |
| [WPF アプリと WinForms アプリで OutputType が WinExe に設定されている](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | 5.0 |
| [WinForms と WPF アプリで Microsoft.NET.Sdk が使用される](#winforms-and-wpf-apps-use-microsoftnetsdk) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

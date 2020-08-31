---
title: 互換性に影響する変更
description: .NET Core の各バージョンの破壊的変更について説明します。
ms.date: 11/27/2019
ms.openlocfilehash: 73c1576aa92f0e236ead0ca1a12ac26efcbf3cbe
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810899"
---
# <a name="breaking-change-selectors"></a>破壊的変更のセレクター

次のバージョンと領域のセレクターでは、.NET Core、ASP.NET Core、EF Core の異なるバージョン間で適用可能な破壊的変更がフィルターして一覧表示されます。 目次でバージョン別やテクノロジ領域別の記事も参照できます。

## <a name="by-version"></a>バージョン別

現在ターゲットにしている .NET のバージョンを選択してから、移行先の .NET Core のバージョンを選択します。

> [!div class="op_multi_selector" title1="ターゲット バージョンから" title2="移行されたバージョンへ"]
>
> - [(3.1 | 5.0)](3.1-5.0.md)
> - [(3.0 | 3.1)](3.0-3.1.md)
> - [(2.2 | 3.1)](2.2-3.1.md)
> - [(2.2 | 3.0)](2.2-3.0.md)
> - [(2.0 | 2.1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a>テクノロジ領域別

関心のある .NET Core テクノロジ領域を選択してください。 個々の変更は .NET Core のバージョン順になっています。

> [!div class="op_single_selector"]
>
> - [ASP.NET Core](aspnetcore.md)
> - [コード分析](code-analysis.md)
> - [Core .NET ライブラリ](corefx.md)
> - [暗号](cryptography.md)
> - [EF Core](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
> - [グローバリゼーション](globalization.md)
> - [Interop](interop.md)
> - [ネットワーク](networking.md)
> - [シリアル化](serialization.md)
> - [Visual Basic](visualbasic.md)
> - [Windows フォーム](winforms.md)

## <a name="github-issues-and-announcements"></a>GitHub のイシューとお知らせ

また、次の GitHub リポジトリでは、.NET Core で導入された破壊的変更について詳しく説明している個々の問題を確認することもできます。

- .NET Core の場合は、[dotnet/ docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) リポジトリ。
- ASP.NET Core の場合は、[aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) リポジトリ。
- Entity Framework Core の場合は、[dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) リポジトリ。

## <a name="see-also"></a>関連項目

- [.NET Framework から .NET Core に移行する](../porting/index.md)

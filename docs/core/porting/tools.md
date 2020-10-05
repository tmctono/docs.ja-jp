---
title: .NET Core に移植するためのツール
description: .NET Core への移植に使用できるいくつかのツールに関する詳細情報
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406129"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>.NET Core への移植で役立つツール

この記事に一覧表示されているツールは、移植するときに役立つ場合があります。

- [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - .NET Framework と .NET Core の間で、コードを
  - [コマンド ライン ツール](https://github.com/Microsoft/dotnet-apiport/releases)として
  - [Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)として、どの程度移植できるかを示すレポートを生成できるツールチェーン。
- [プラットフォーム互換性アナライザー](../../standard/analyzers/platform-compat-analyzer.md) - API を使用できない可能性のある呼び出しサイトからプラットフォーム固有の API を使用するときに開発者に通知する Roslyn アナライザーです。
- [.NET API アナライザー](../../standard/analyzers/api-analyzer.md) - クロスプラットフォームのアプリとライブラリにおいてプラットフォームの互換性に関する問題を検出するのに役立つ Roslyn アナライザー。
- [try-convert](https://www.nuget.org/packages/try-convert/) - デスクトップ アプリを .NET Core に移動するなど、プロジェクトかソリューション全体を .NET SDK に変換できる .NET Core グローバル ツール。 もっと複雑なビルドを確立し (カスタムのタスク、ターゲット、インポートなど)、.NET Core との間で互換性がない多くのプロジェクト タイプが拒否される場合は推奨されません。

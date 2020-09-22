---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606933"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute は、WinMD のシナリオで、ObsoleteAttribute と DeprecatedAttribute の両方としてエクスポートする

#### <a name="details"></a>説明

Windows メタデータ ライブラリ (.winmd ファイル) を作成するとき、<xref:System.ObsoleteAttribute?displayProperty=fullName> 属性は <xref:System.ObsoleteAttribute?displayProperty=fullName> および [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方としてエクスポートされます。

#### <a name="suggestion"></a>提案される解決策

<xref:System.ObsoleteAttribute?displayProperty=fullName> 属性を使用する既存のソース コードを再コンパイルするとき、C++/CX または JavaScript からそのコードを使用するとき、警告が生成されることがあります。マネージド アセンブリのコードを記述するとき、<xref:System.ObsoleteAttribute?displayProperty=fullName> と [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方を適用することはお勧めしません。ビルドで警告が生成されることがあります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   | エッジ        |
| バージョン | 4.5.1       |
| 種類    | 再ターゲット中 |

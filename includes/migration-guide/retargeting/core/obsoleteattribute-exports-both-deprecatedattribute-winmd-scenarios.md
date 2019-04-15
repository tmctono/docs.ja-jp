---
ms.openlocfilehash: e8c48c4b1031813ce62f576e5bf1f94c082dfe4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234700"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="32ea0-101">ObsoleteAttribute は、WinMD のシナリオで、ObsoleteAttribute と DeprecatedAttribute の両方としてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="32ea0-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

|   |   |
|---|---|
|<span data-ttu-id="32ea0-102">説明</span><span class="sxs-lookup"><span data-stu-id="32ea0-102">Details</span></span>|<span data-ttu-id="32ea0-103">Windows メタデータ ライブラリ (.winmd ファイル) を作成するとき、<xref:System.ObsoleteAttribute?displayProperty=name> 属性は <xref:System.ObsoleteAttribute?displayProperty=name> および [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方としてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="32ea0-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=name> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=name> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>|
|<span data-ttu-id="32ea0-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="32ea0-104">Suggestion</span></span>|<span data-ttu-id="32ea0-105"><xref:System.ObsoleteAttribute?displayProperty=name> 属性を使用する既存のソース コードを再コンパイルするとき、C++/CX または JavaScript からそのコードを使用するとき、警告が生成されることがあります。マネージド アセンブリのコードを記述するとき、<xref:System.ObsoleteAttribute?displayProperty=name> と [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方を適用することはお勧めしません。ビルドで警告が生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="32ea0-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=name> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=name> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>|
|<span data-ttu-id="32ea0-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="32ea0-106">Scope</span></span>|<span data-ttu-id="32ea0-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="32ea0-107">Edge</span></span>|
|<span data-ttu-id="32ea0-108">Version</span><span class="sxs-lookup"><span data-stu-id="32ea0-108">Version</span></span>|<span data-ttu-id="32ea0-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="32ea0-109">4.5.1</span></span>|
|<span data-ttu-id="32ea0-110">型</span><span class="sxs-lookup"><span data-stu-id="32ea0-110">Type</span></span>|<span data-ttu-id="32ea0-111">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="32ea0-111">Retargeting</span></span>|

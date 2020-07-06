---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616120"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="3d36c-101">ObsoleteAttribute は、WinMD のシナリオで、ObsoleteAttribute と DeprecatedAttribute の両方としてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3d36c-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="3d36c-102">説明</span><span class="sxs-lookup"><span data-stu-id="3d36c-102">Details</span></span>

<span data-ttu-id="3d36c-103">Windows メタデータ ライブラリ (.winmd ファイル) を作成するとき、<xref:System.ObsoleteAttribute?displayProperty=fullName> 属性は <xref:System.ObsoleteAttribute?displayProperty=fullName> および [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方としてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="3d36c-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3d36c-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="3d36c-104">Suggestion</span></span>

<span data-ttu-id="3d36c-105"><xref:System.ObsoleteAttribute?displayProperty=fullName> 属性を使用する既存のソース コードを再コンパイルするとき、C++/CX または JavaScript からそのコードを使用するとき、警告が生成されることがあります。マネージド アセンブリのコードを記述するとき、<xref:System.ObsoleteAttribute?displayProperty=fullName> と [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方を適用することはお勧めしません。ビルドで警告が生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3d36c-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="3d36c-106">名前</span><span class="sxs-lookup"><span data-stu-id="3d36c-106">Name</span></span>    | <span data-ttu-id="3d36c-107">[値]</span><span class="sxs-lookup"><span data-stu-id="3d36c-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3d36c-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="3d36c-108">Scope</span></span>   | <span data-ttu-id="3d36c-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="3d36c-109">Edge</span></span>        |
| <span data-ttu-id="3d36c-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="3d36c-110">Version</span></span> | <span data-ttu-id="3d36c-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3d36c-111">4.5.1</span></span>       |
| <span data-ttu-id="3d36c-112">種類</span><span class="sxs-lookup"><span data-stu-id="3d36c-112">Type</span></span>    | <span data-ttu-id="3d36c-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="3d36c-113">Retargeting</span></span> |

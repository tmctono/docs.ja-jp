---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606933"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="26748-101">ObsoleteAttribute は、WinMD のシナリオで、ObsoleteAttribute と DeprecatedAttribute の両方としてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="26748-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="26748-102">説明</span><span class="sxs-lookup"><span data-stu-id="26748-102">Details</span></span>

<span data-ttu-id="26748-103">Windows メタデータ ライブラリ (.winmd ファイル) を作成するとき、<xref:System.ObsoleteAttribute?displayProperty=fullName> 属性は <xref:System.ObsoleteAttribute?displayProperty=fullName> および [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方としてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="26748-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="26748-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="26748-104">Suggestion</span></span>

<span data-ttu-id="26748-105"><xref:System.ObsoleteAttribute?displayProperty=fullName> 属性を使用する既存のソース コードを再コンパイルするとき、C++/CX または JavaScript からそのコードを使用するとき、警告が生成されることがあります。マネージド アセンブリのコードを記述するとき、<xref:System.ObsoleteAttribute?displayProperty=fullName> と [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) の両方を適用することはお勧めしません。ビルドで警告が生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="26748-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="26748-106">名前</span><span class="sxs-lookup"><span data-stu-id="26748-106">Name</span></span>    | <span data-ttu-id="26748-107">[値]</span><span class="sxs-lookup"><span data-stu-id="26748-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="26748-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="26748-108">Scope</span></span>   | <span data-ttu-id="26748-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="26748-109">Edge</span></span>        |
| <span data-ttu-id="26748-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="26748-110">Version</span></span> | <span data-ttu-id="26748-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="26748-111">4.5.1</span></span>       |
| <span data-ttu-id="26748-112">種類</span><span class="sxs-lookup"><span data-stu-id="26748-112">Type</span></span>    | <span data-ttu-id="26748-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="26748-113">Retargeting</span></span> |

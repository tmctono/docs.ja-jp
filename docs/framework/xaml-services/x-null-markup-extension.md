---
title: x:Null のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938914"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="c8458-102">x:Null のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="c8458-102">x:Null Markup Extension</span></span>
<span data-ttu-id="c8458-103">指定します`null`XAML メンバーの値として。</span><span class="sxs-lookup"><span data-stu-id="c8458-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c8458-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="c8458-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="c8458-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8458-105">Remarks</span></span>  
 <span data-ttu-id="c8458-106">Null 参照のキーワードC#と[!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)]が null です。</span><span class="sxs-lookup"><span data-stu-id="c8458-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="c8458-107">Null 参照の Microsoft Visual Basic のキーワードは、 `Nothing`、常に使用するが、`{x:Null}`として XAML 使用量に関係なく、XAML と関連付けた分離コード言語。</span><span class="sxs-lookup"><span data-stu-id="c8458-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="c8458-108">`x:Null`マークアップ拡張機能には、設定可能なプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="c8458-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="c8458-109">Null の使用は、CLR の XAML メンバーの露出を関連付け、<xref:System.Nullable%601>値。</span><span class="sxs-lookup"><span data-stu-id="c8458-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="c8458-110">`x:Null`マークアップ拡張機能のすべての XAML マークアップ拡張機能のように、中かっこを使用して (`{,}`) 以外のリテラルまたはイベント ハンドラーの参照属性の値の処理をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="c8458-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="c8458-111">属性構文は、このマークアップ拡張機能で最もよく使用される構文です。</span><span class="sxs-lookup"><span data-stu-id="c8458-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="c8458-112">オブジェクト要素構文`<x:Null />`は技術的には可能ですが、あまり使われないため、`x:Null`マークアップ拡張機能には、位置指定パラメーターまたは構築引数がありません。</span><span class="sxs-lookup"><span data-stu-id="c8458-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="c8458-113">マークアップ拡張機能については、次を参照してください。[マークアップ拡張機能と WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8458-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="c8458-114">このマークアップ拡張機能の処理がによって定義されている .NET Framework XAML サービスを<xref:System.Windows.Markup.NullExtension>クラス。</span><span class="sxs-lookup"><span data-stu-id="c8458-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c8458-115">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="c8458-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="c8458-116">なお`null`参照型の依存関係プロパティの初期設定されていない値とは限りません。</span><span class="sxs-lookup"><span data-stu-id="c8458-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="c8458-117">既定の初期値は、依存関係プロパティごとに異なることができ、プロパティ固有のメタデータに基づくことができます。</span><span class="sxs-lookup"><span data-stu-id="c8458-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="c8458-118">多くの依存関係プロパティが受け入れない`null`マークアップまたはコードの検証コールバックの実装のための値として。</span><span class="sxs-lookup"><span data-stu-id="c8458-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="c8458-119">依存関係プロパティの詳細については、次を参照してください。[依存関係プロパティの概要](../wpf/advanced/dependency-properties-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8458-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8458-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8458-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="c8458-121">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="c8458-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="c8458-122">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="c8458-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)

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
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432696"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="f2bd2-102">x:Null のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="f2bd2-102">x:Null Markup Extension</span></span>

<span data-ttu-id="f2bd2-103">XAML`null`メンバーの値として指定します。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="f2bd2-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="f2bd2-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="f2bd2-105">解説</span><span class="sxs-lookup"><span data-stu-id="f2bd2-105">Remarks</span></span>

<span data-ttu-id="f2bd2-106">C# および C++ の null 参照のキーワードは null です。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="f2bd2-107">Null 参照の Visual Basic キーワード`Nothing`は で、XAML`{x:Null}`に関連付ける分離コード言語に関係なく、常に XAML の使用方法として使用します。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="f2bd2-108">`x:Null`マークアップ拡張機能には、設定可能なプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="f2bd2-109">NULL の使用は、多くの場合、CLR<xref:System.Nullable%601>値の XAML メンバーの公開に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="f2bd2-110">マークアップ`x:Null`拡張機能は、すべての XAML マークアップ拡張機能と同様に、リテラル`{,}`やイベント ハンドラー参照以外の属性値の処理をエスケープするために中かっこ ( ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="f2bd2-111">属性構文は、このマークアップ拡張機能で最もよく使用される構文です。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="f2bd2-112">オブジェクト要素構文`<x:Null />`は技術的には可能ですが、`x:Null`マークアップ拡張機能には位置指定パラメータや構築引数がないため、ほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="f2bd2-113">マークアップ拡張機能の詳細については、「[マークアップ拡張機能と WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="f2bd2-114">NET XAML サービスでは、このマークアップ拡張機能の処理は、クラスによって定義<xref:System.Windows.Markup.NullExtension>されます。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="f2bd2-115">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="f2bd2-115">WPF Usage Notes</span></span>

<span data-ttu-id="f2bd2-116">参照型`null`の依存関係プロパティの初期の未設定値である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="f2bd2-117">初期既定値は、依存関係プロパティごとに異なる場合があり、プロパティ固有のメタデータに基づいて設定できます。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="f2bd2-118">多くの依存関係プロパティは、`null`検証コールバックの実装により、マークアップまたはコードを使用して値として受け入れれません。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="f2bd2-119">依存関係プロパティの詳細については、「[依存関係プロパティの概要](../../framework/wpf/advanced/dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2bd2-119">For more information about dependency properties, see [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2bd2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2bd2-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="f2bd2-121">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2bd2-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="f2bd2-122">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="f2bd2-122">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

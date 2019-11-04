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
ms.openlocfilehash: ff82b0bfc1983240431e582dbd78778dc4469241
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459937"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="2924a-102">x:Null のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="2924a-102">x:Null Markup Extension</span></span>
<span data-ttu-id="2924a-103">XAML メンバーの値として `null` を指定します。</span><span class="sxs-lookup"><span data-stu-id="2924a-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2924a-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="2924a-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="2924a-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="2924a-105">Remarks</span></span>  
 <span data-ttu-id="2924a-106">およびC# C++内の null 参照のキーワードが null です。</span><span class="sxs-lookup"><span data-stu-id="2924a-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="2924a-107">Null 参照の Microsoft Visual Basic キーワードは `Nothing`ですが、XAML に関連付ける分離コード言語に関係なく、常に `{x:Null}` を XAML の使用として使用します。</span><span class="sxs-lookup"><span data-stu-id="2924a-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="2924a-108">`x:Null` マークアップ拡張機能には、設定可能なプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="2924a-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="2924a-109">Null 使用は、多くの場合、CLR <xref:System.Nullable%601> 値の XAML メンバー公開に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="2924a-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="2924a-110">すべての XAML マークアップ拡張機能と同様に、`x:Null` マークアップ拡張機能は、中かっこ (`{,}`) を使用して、リテラルまたはイベントハンドラー参照以外の属性値の処理をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="2924a-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="2924a-111">属性構文は、このマークアップ拡張機能で最も頻繁に使用される構文です。</span><span class="sxs-lookup"><span data-stu-id="2924a-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="2924a-112">オブジェクト要素の構文 `<x:Null />` は技術的には可能ですが、`x:Null` マークアップ拡張機能に位置指定パラメーターも構築引数もないため、ほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="2924a-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="2924a-113">マークアップ拡張機能の詳細については、「[マークアップ拡張機能と WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2924a-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="2924a-114">.NET Framework XAML サービスでは、このマークアップ拡張機能の処理は <xref:System.Windows.Markup.NullExtension> クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2924a-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="2924a-115">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="2924a-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="2924a-116">`null` は、必ずしも参照型の依存関係プロパティの最初の未設定値ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2924a-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="2924a-117">初期の既定値は、依存関係プロパティごとに異なる場合があり、プロパティ固有のメタデータに基づいている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2924a-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="2924a-118">多くの依存関係プロパティは、検証コールバックの実装により、マークアップまたはコードを使用して、`null` を値として受け入れません。</span><span class="sxs-lookup"><span data-stu-id="2924a-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="2924a-119">依存関係プロパティの詳細については、「[依存関係プロパティの概要](../wpf/advanced/dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2924a-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2924a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2924a-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="2924a-121">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="2924a-121">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="2924a-122">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="2924a-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)

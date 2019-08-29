---
title: ThemeDictionary のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: 7fa729d600f25b73028bae0dd6d9248b5839dd4c
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133860"
---
# <a name="themedictionary-markup-extension"></a><span data-ttu-id="81c93-102">ThemeDictionary のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="81c93-102">ThemeDictionary Markup Extension</span></span>
<span data-ttu-id="81c93-103">カスタムコントロールの作成者またはサードパーティのコントロールを統合して、コントロールのスタイル設定に使用するテーマ固有のリソースディクショナリを読み込む方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="81c93-103">Provides a way for custom control authors or applications that integrate third-party controls to load theme-specific resource dictionaries to use in styling the control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="81c93-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="81c93-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="81c93-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="81c93-105">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="81c93-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="81c93-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`assemblyUri`|<span data-ttu-id="81c93-107">テーマ情報を格納しているアセンブリの。[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c93-107">The [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] of the assembly that contains theme information.</span></span> <span data-ttu-id="81c93-108">通常、これは、大きなパッケージ内のアセンブリを参照するパック URI です。</span><span class="sxs-lookup"><span data-stu-id="81c93-108">Typically, this is a pack URI that references an assembly in the larger package.</span></span> <span data-ttu-id="81c93-109">アセンブリリソースとパック Uri は、デプロイの問題を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="81c93-109">Assembly resources and pack URIs simplify deployment issues.</span></span> <span data-ttu-id="81c93-110">詳細については、「 [WPF のパック uri](../app-development/pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81c93-110">For more information see [Pack URIs in WPF](../app-development/pack-uris-in-wpf.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81c93-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="81c93-111">Remarks</span></span>  
 <span data-ttu-id="81c93-112">この拡張機能は、1つの特定のプロパティ値 (の値<xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>) のみを埋めることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="81c93-112">This extension is intended to fill only one specific property value: a value for <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="81c93-113">この拡張機能を使用すると、1つのリソースのみのアセンブリを指定できます。このアセンブリには、Windows Aero テーマがユーザーのシステムに適用されている場合にのみ使用し、他のスタイルは、Luna テーマがアクティブになっている場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="81c93-113">By using this extension, you can specify a single resources-only assembly that contains some styles to use only when the Windows Aero theme is applied to the user's system, other styles only when the Luna theme is active, and so on.</span></span> <span data-ttu-id="81c93-114">この拡張機能を使用すると、必要に応じて、コントロール固有のリソースディクショナリの内容を自動的に無効にして、別のテーマに合わせて再度読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="81c93-114">By using this extension, the contents of a control-specific resource dictionary can be automatically invalidated and reloaded to be specific for another theme when required.</span></span>  
  
 <span data-ttu-id="81c93-115">文字列`assemblyUri` (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>プロパティ値) は、特定のテーマに適用される辞書を識別する名前付け規則の基礎となります。</span><span class="sxs-lookup"><span data-stu-id="81c93-115">The `assemblyUri` string (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property value) forms the basis of a naming convention that identifies which dictionary applies for a particular theme.</span></span> <span data-ttu-id="81c93-116">の<xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]ロジックでは、プリコンパイル済みリソースアセンブリに含まれているように、特定のテーマディクショナリバリアントを指すを生成することによって規則を完成させることができます。 `ThemeDictionary`</span><span class="sxs-lookup"><span data-stu-id="81c93-116">The <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logic for `ThemeDictionary` completes the convention by generating a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] that points to a particular theme dictionary variant, as contained within a precompiled resource assembly.</span></span> <span data-ttu-id="81c93-117">ここでは、この規則の説明、一般的なコントロールのスタイル設定とページ/アプリケーションレベルのスタイル設定とのテーマの相互作用については説明しません。</span><span class="sxs-lookup"><span data-stu-id="81c93-117">Describing this convention, or theme interactions with general control styling and page/application level styling as a concept, is not covered fully here.</span></span> <span data-ttu-id="81c93-118">を使用`ThemeDictionary`するための基本的なシナリオは、アプリケーションレベル`ResourceDictionary`で宣言されたの<xref:System.Windows.ResourceDictionary.Source%2A>プロパティを指定することです。</span><span class="sxs-lookup"><span data-stu-id="81c93-118">The basic scenario for using `ThemeDictionary` is to specify the <xref:System.Windows.ResourceDictionary.Source%2A> property of a `ResourceDictionary` declared at the application level.</span></span> <span data-ttu-id="81c93-119">直接[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] `ThemeDictionary`ではなく、拡張機能を使用してアセンブリにを指定すると、拡張ロジックによって、システムテーマが変更されるたびに適用される無効化ロジックが提供されます。 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c93-119">When you provide a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the assembly through a `ThemeDictionary` extension rather than as a direct [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], the extension logic will provide invalidation logic that applies whenever the system theme changes.</span></span>  
  
 <span data-ttu-id="81c93-120">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="81c93-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="81c93-121">`ThemeDictionary` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 拡張クラスの <xref:System.Windows.ThemeDictionaryExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="81c93-121">The string token provided after the `ThemeDictionary` identifier string is assigned as the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> value of the underlying <xref:System.Windows.ThemeDictionaryExtension> extension class.</span></span>  
  
 <span data-ttu-id="81c93-122">`ThemeDictionary`オブジェクト要素の構文でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="81c93-122">`ThemeDictionary` may also be used in object element syntax.</span></span> <span data-ttu-id="81c93-123">この場合、 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>プロパティの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81c93-123">In this case, specifying the value of the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property is required.</span></span>  
  
 <span data-ttu-id="81c93-124">`ThemeDictionary` は、<xref:System.Windows.Markup.StaticExtension.Member%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="81c93-124">`ThemeDictionary` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.Markup.StaticExtension.Member%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 <span data-ttu-id="81c93-125">詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="81c93-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="81c93-126">`ThemeDictionary` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="81c93-126">Because `ThemeDictionary` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="81c93-127">プロセッサ実装では、このマークアップ<xref:System.Windows.ThemeDictionaryExtension>拡張機能の処理はクラスによって定義されます。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c93-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.ThemeDictionaryExtension> class.</span></span>  
  
 <span data-ttu-id="81c93-128">`ThemeDictionary` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="81c93-128">`ThemeDictionary` is a markup extension.</span></span> <span data-ttu-id="81c93-129">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="81c93-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="81c93-130">のすべての[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ拡張機能は、属性構文で {および} 文字を使用します。これ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]は、マークアップ拡張機能が属性を処理する必要があることをプロセッサが認識する規則です。</span><span class="sxs-lookup"><span data-stu-id="81c93-130">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="81c93-131">詳細については、「[マークアップ拡張機能」および「WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81c93-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c93-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="81c93-132">See also</span></span>

- [<span data-ttu-id="81c93-133">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="81c93-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="81c93-134">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="81c93-134">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="81c93-135">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="81c93-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="81c93-136">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="81c93-136">WPF Application Resource, Content, and Data Files</span></span>](../app-development/wpf-application-resource-content-and-data-files.md)

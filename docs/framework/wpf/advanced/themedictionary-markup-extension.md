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
ms.openlocfilehash: 450956de1c7498bf2b92096b38ad2f64745a0b2d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141097"
---
# <a name="themedictionary-markup-extension"></a><span data-ttu-id="b7d38-102">ThemeDictionary のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="b7d38-102">ThemeDictionary Markup Extension</span></span>
<span data-ttu-id="b7d38-103">カスタム コントロールの作成者またはサードパーティのコントロールを統合するアプリケーションに、コントロールのスタイル設定に使用するテーマ固有のリソース ディクショナリを読み込む方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7d38-103">Provides a way for custom control authors or applications that integrate third-party controls to load theme-specific resource dictionaries to use in styling the control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b7d38-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="b7d38-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="b7d38-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="b7d38-105">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b7d38-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="b7d38-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`assemblyUri`|<span data-ttu-id="b7d38-107">テーマの情報が格納されているアセンブリの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="b7d38-107">The uniform resource identifier (URI) of the assembly that contains theme information.</span></span> <span data-ttu-id="b7d38-108">通常、これは大きなパッケージ内のアセンブリを参照するパック URI です。</span><span class="sxs-lookup"><span data-stu-id="b7d38-108">Typically, this is a pack URI that references an assembly in the larger package.</span></span> <span data-ttu-id="b7d38-109">アセンブリ リソースとパック URI によって、配置の問題が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="b7d38-109">Assembly resources and pack URIs simplify deployment issues.</span></span> <span data-ttu-id="b7d38-110">詳細については、「[WPF におけるパッケージの URI](../app-development/pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7d38-110">For more information see [Pack URIs in WPF](../app-development/pack-uris-in-wpf.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d38-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7d38-111">Remarks</span></span>  
 <span data-ttu-id="b7d38-112">この拡張機能では、1 つの特定のプロパティ値、つまり <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType> の値を設定することだけが意図されています。</span><span class="sxs-lookup"><span data-stu-id="b7d38-112">This extension is intended to fill only one specific property value: a value for <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b7d38-113">この拡張機能を使用すると、単一リソースのみのアセンブリを指定できます。それには、Windows Aero テーマがユーザーのシステムに適用されている場合にのみ使用されるスタイル、Luna テーマがアクティブになっている場合にのみ使用される他のスタイル、などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-113">By using this extension, you can specify a single resources-only assembly that contains some styles to use only when the Windows Aero theme is applied to the user's system, other styles only when the Luna theme is active, and so on.</span></span> <span data-ttu-id="b7d38-114">この拡張機能を使用することで、必要に応じて、コントロール固有のリソース ディクショナリの内容を自動的に無効にし、別のテーマに合わせて再度読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-114">By using this extension, the contents of a control-specific resource dictionary can be automatically invalidated and reloaded to be specific for another theme when required.</span></span>  
  
 <span data-ttu-id="b7d38-115">`assemblyUri` の文字列 (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> プロパティの値) は、特定のテーマに適用されるディクショナリを識別する名前付け規則の基礎となります。</span><span class="sxs-lookup"><span data-stu-id="b7d38-115">The `assemblyUri` string (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property value) forms the basis of a naming convention that identifies which dictionary applies for a particular theme.</span></span> <span data-ttu-id="b7d38-116">`ThemeDictionary` に対する <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> のロジックにより、プリコンパイル済みのリソース アセンブリに含まれる、特定のテーマ ディクショナリのバリエーションを指す Uniform Resource Identifier (URI) を生成することによって、規則が完成されます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-116">The <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logic for `ThemeDictionary` completes the convention by generating a uniform resource identifier (URI) that points to a particular theme dictionary variant, as contained within a precompiled resource assembly.</span></span> <span data-ttu-id="b7d38-117">この規則、または一般的なコントロールのスタイル設定およびページやアプリケーション レベルのスタイル設定とのテーマの相互作用の概念については、ここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="b7d38-117">Describing this convention, or theme interactions with general control styling and page/application level styling as a concept, is not covered fully here.</span></span> <span data-ttu-id="b7d38-118">`ThemeDictionary` を使用する基本的なシナリオは、アプリケーション レベルで宣言された `ResourceDictionary` の <xref:System.Windows.ResourceDictionary.Source%2A> プロパティを指定する場合です。</span><span class="sxs-lookup"><span data-stu-id="b7d38-118">The basic scenario for using `ThemeDictionary` is to specify the <xref:System.Windows.ResourceDictionary.Source%2A> property of a `ResourceDictionary` declared at the application level.</span></span> <span data-ttu-id="b7d38-119">ダイレクト URI ではなく `ThemeDictionary` 拡張を使用してアセンブリの URI を指定すると、システム テーマが変更されるたびに適用される無効化ロジックが拡張ロジックによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-119">When you provide a URI for the assembly through a `ThemeDictionary` extension rather than as a direct URI, the extension logic will provide invalidation logic that applies whenever the system theme changes.</span></span>  
  
 <span data-ttu-id="b7d38-120">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="b7d38-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="b7d38-121">`ThemeDictionary` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 拡張クラスの <xref:System.Windows.ThemeDictionaryExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-121">The string token provided after the `ThemeDictionary` identifier string is assigned as the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> value of the underlying <xref:System.Windows.ThemeDictionaryExtension> extension class.</span></span>  
  
 <span data-ttu-id="b7d38-122">`ThemeDictionary` は、オブジェクト要素構文でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-122">`ThemeDictionary` may also be used in object element syntax.</span></span> <span data-ttu-id="b7d38-123">この場合は、<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> プロパティの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d38-123">In this case, specifying the value of the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property is required.</span></span>  
  
 <span data-ttu-id="b7d38-124">`ThemeDictionary` は、<xref:System.Windows.Markup.StaticExtension.Member%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-124">`ThemeDictionary` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.Markup.StaticExtension.Member%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" ... />  
```  
  
 <span data-ttu-id="b7d38-125">詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="b7d38-126">`ThemeDictionary` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="b7d38-126">Because `ThemeDictionary` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="b7d38-127">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサの実装では、このマークアップ拡張の処理は <xref:System.Windows.ThemeDictionaryExtension> クラスによって定義されています。</span><span class="sxs-lookup"><span data-stu-id="b7d38-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.ThemeDictionaryExtension> class.</span></span>  
  
 <span data-ttu-id="b7d38-128">`ThemeDictionary` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="b7d38-128">`ThemeDictionary` is a markup extension.</span></span> <span data-ttu-id="b7d38-129">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="b7d38-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="b7d38-130">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のすべてのマークアップ拡張では、それぞれの属性構文で { と } の 2 つの記号が使用されます。これは規約であり、これに従って [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサでは、マークアップ拡張で属性を処理する必要があることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="b7d38-130">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="b7d38-131">詳細については、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7d38-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d38-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7d38-132">See also</span></span>

- [<span data-ttu-id="b7d38-133">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b7d38-133">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b7d38-134">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="b7d38-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="b7d38-135">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="b7d38-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="b7d38-136">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="b7d38-136">WPF Application Resource, Content, and Data Files</span></span>](../app-development/wpf-application-resource-content-and-data-files.md)

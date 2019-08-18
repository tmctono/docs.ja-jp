---
title: mc:Ignorable 属性
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: e99ca09d51f3ba6c01b9e400bfba00749faf62b3
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567439"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="c5335-102">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="c5335-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="c5335-103">マークアップファイルで検出された[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 名前空間プレフィックスがプロセッサによって無視される可能性があるかどうかを指定します。[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5335-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="c5335-104">属性`mc:Ignorable`は、カスタム名前空間マッピング[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]とバージョン管理の両方で、マークアップ互換性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c5335-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="c5335-105">XAML 属性の使用法 (単一のプレフィックス)</span><span class="sxs-lookup"><span data-stu-id="c5335-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="c5335-106">XAML 属性の使用法 (2 つのプレフィックス)</span><span class="sxs-lookup"><span data-stu-id="c5335-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c5335-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="c5335-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c5335-108">*ignorablePrefix、ignorablePrefix1、その他*</span><span class="sxs-lookup"><span data-stu-id="c5335-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="c5335-109">XML 1.0 仕様に従って、任意の有効なプレフィックス文字列。</span><span class="sxs-lookup"><span data-stu-id="c5335-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="c5335-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="c5335-110">*ignorableUri*</span></span>|<span data-ttu-id="c5335-111">XML 1.0 仕様に従って、名前空間を指定するための任意の有効な URI。</span><span class="sxs-lookup"><span data-stu-id="c5335-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="c5335-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="c5335-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="c5335-113">基になる型を解決でき[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ない場合に、プロセッサ実装によって無視される可能性がある要素。</span><span class="sxs-lookup"><span data-stu-id="c5335-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5335-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5335-114">Remarks</span></span>  
 <span data-ttu-id="c5335-115">名前空間プレフィックスは、互換性名前空間[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]を[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マップするときに使用する推奨プレフィックス表記規則です。 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5335-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="c5335-116">要素名のプレフィックス部分がとして`mc:Ignorable`識別される要素または属性は、 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサによる処理時にエラーを発生させません。</span><span class="sxs-lookup"><span data-stu-id="c5335-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="c5335-117">その属性を基になる型またはプログラミング構成体に解決できなかった場合、その要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c5335-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="c5335-118">ただし、無視された要素では、その要素が処理されないという副作用を伴う追加の要素の要件に対して、追加の解析エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5335-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="c5335-119">たとえば、特定の要素のコンテンツモデルでは、1つの子要素だけが必要になる場合があり`mc:Ignorable`ますが、指定された子要素がプレフィックスに含まれていて[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 、指定された子要素が型に解決されない場合、プロセッサは次のようになります。エラーを発生させます。</span><span class="sxs-lookup"><span data-stu-id="c5335-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="c5335-120">`mc:Ignorable`識別子文字列への名前空間マッピングにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c5335-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="c5335-121">`mc:Ignorable`アセンブリへの名前空間マッピングには適用されません。アセンブリは、CLR 名前空間とアセンブリを指定します (または、現在の実行可能ファイルをアセンブリとして既定値として指定します)。</span><span class="sxs-lookup"><span data-stu-id="c5335-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="c5335-122">プロセッサを[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]実装する場合、として識別されるプレフィックスによって修飾されている要素または属性の型解決では、プロセッサ実装で解析`mc:Ignorable`または処理エラーが発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5335-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="c5335-123">しかし、プロセッサの実装では、前に示した1つの子要素の例のように、要素の読み込みまたは処理に失敗した場合の二次的な結果である例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5335-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="c5335-124">既定では、 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサは無視された要素内のコンテンツを無視します。</span><span class="sxs-lookup"><span data-stu-id="c5335-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="c5335-125">ただし、追加の属性である[mc: ProcessContent 属性](mc-processcontent-attribute.md)を指定して、次に使用可能な親要素によって無視された要素内のコンテンツを継続して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5335-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="c5335-126">属性では、1つ以上の空白文字を区切り記号として使用することで、複数のプレフィックス`mc:Ignorable="ignore1 ignore2"`を指定できます。たとえば、のようになります。</span><span class="sxs-lookup"><span data-stu-id="c5335-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="c5335-127">名前[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]空間は、SDK のこの領域内には記載されていない他の要素と属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="c5335-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="c5335-128">詳細については、「 [XML マークアップ互換性の仕様](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5335-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5335-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5335-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="c5335-130">PresentationOptions:Freeze 属性</span><span class="sxs-lookup"><span data-stu-id="c5335-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="c5335-131">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="c5335-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="c5335-132">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="c5335-132">Documents in WPF</span></span>](documents-in-wpf.md)

---
title: mc:ProcessContent 属性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bcf55668bdc70902e346c401549a88f6ccb9072e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095126"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="92ef1-102">mc:ProcessContent 属性</span><span class="sxs-lookup"><span data-stu-id="92ef1-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="92ef1-103">[mc:Ignorable 属性](mc-ignorable-attribute.md)を指定することで直接の親要素が [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサによって無視される場合でも、関連する親要素によってコンテンツが処理される必要がある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="92ef1-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="92ef1-104">`mc:ProcessContent` 属性は、カスタムの名前空間マッピングと [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のバージョン管理の両方で、マークアップ互換性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="92ef1-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="92ef1-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="92ef1-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="92ef1-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="92ef1-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92ef1-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="92ef1-107">*ignorablePrefix*</span></span>|<span data-ttu-id="92ef1-108">XML 1.0 仕様に従う有効なプレフィックス文字列。</span><span class="sxs-lookup"><span data-stu-id="92ef1-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="92ef1-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="92ef1-109">*ignorableUri*</span></span>|<span data-ttu-id="92ef1-110">XML 1.0 仕様に従う、名前空間を指定するための有効な URI。</span><span class="sxs-lookup"><span data-stu-id="92ef1-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="92ef1-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="92ef1-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="92ef1-112">基になる型を解決できない場合に、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] プロセッサ実装によって無視できる要素。</span><span class="sxs-lookup"><span data-stu-id="92ef1-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="92ef1-113">*[content]*</span><span class="sxs-lookup"><span data-stu-id="92ef1-113">*[content]*</span></span>|<span data-ttu-id="92ef1-114">*ThisElementCanBeIgnored* は無視可能とマークされています。</span><span class="sxs-lookup"><span data-stu-id="92ef1-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="92ef1-115">プロセッサによってその要素が無視された場合、 *[content]* は *object* によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="92ef1-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92ef1-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="92ef1-116">Remarks</span></span>  
 <span data-ttu-id="92ef1-117">既定で [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサでは、無視された要素内のコンテンツは無視されます。</span><span class="sxs-lookup"><span data-stu-id="92ef1-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="92ef1-118">`mc:ProcessContent` を使用して特定の要素を指定すると、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサでは、無視された要素内のコンテンツが引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="92ef1-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="92ef1-119">通常、これは、コンテンツが複数のタグ内に入れ子にされ、少なくとも 1 つのタグが無視可能で、少なくとも 1 つは無視可能ではない場合に使用されます。ません。</span><span class="sxs-lookup"><span data-stu-id="92ef1-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="92ef1-120">スペース区切りを使用して、属性に複数のプレフィックスを指定できます (例: `mc:ProcessContent="ignore:Element1 ignore:Element2"`)。</span><span class="sxs-lookup"><span data-stu-id="92ef1-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="92ef1-121">`http://schemas.openxmlformats.org/markup-compatibility/2006` 名前空間には、SDK のこの領域ではドキュメント化されていない他の要素と属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="92ef1-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="92ef1-122">詳細については、[XML マークアップ互換性仕様](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ef1-122">For more information, see [XML Markup Compatibility Specification](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ef1-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="92ef1-123">See also</span></span>

- [<span data-ttu-id="92ef1-124">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="92ef1-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="92ef1-125">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="92ef1-125">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)

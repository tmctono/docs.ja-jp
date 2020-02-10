---
title: mc:ProcessContent 属性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bcf55668bdc70902e346c401549a88f6ccb9072e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095126"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="4d65b-102">mc:ProcessContent 属性</span><span class="sxs-lookup"><span data-stu-id="4d65b-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="4d65b-103">[Mc: Ignorable 属性](mc-ignorable-attribute.md)を指定することにより、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のプロセッサによって直接の親要素が無視される可能性がある場合でも、関連する親要素によって処理されるコンテンツを保持する [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d65b-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="4d65b-104">`mc:ProcessContent` 属性は、カスタム名前空間マッピングと [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] バージョン管理の両方で、マークアップ互換性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4d65b-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="4d65b-105">XAML 属性の使用</span><span class="sxs-lookup"><span data-stu-id="4d65b-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="4d65b-106">XAML の値</span><span class="sxs-lookup"><span data-stu-id="4d65b-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d65b-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="4d65b-107">*ignorablePrefix*</span></span>|<span data-ttu-id="4d65b-108">XML 1.0 仕様に従って、任意の有効なプレフィックス文字列。</span><span class="sxs-lookup"><span data-stu-id="4d65b-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="4d65b-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="4d65b-109">*ignorableUri*</span></span>|<span data-ttu-id="4d65b-110">XML 1.0 仕様に従って、名前空間を指定するための任意の有効な URI。</span><span class="sxs-lookup"><span data-stu-id="4d65b-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="4d65b-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="4d65b-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="4d65b-112">基になる型を解決できない場合に [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] のプロセッサ実装によって無視される要素。</span><span class="sxs-lookup"><span data-stu-id="4d65b-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="4d65b-113">*情報*</span><span class="sxs-lookup"><span data-stu-id="4d65b-113">*[content]*</span></span>|<span data-ttu-id="4d65b-114">*ThisElementCanBeIgnored*は無視としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="4d65b-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="4d65b-115">プロセッサがその要素を無視した場合、 *[content]* は*オブジェクト*によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="4d65b-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d65b-116">解説</span><span class="sxs-lookup"><span data-stu-id="4d65b-116">Remarks</span></span>  
 <span data-ttu-id="4d65b-117">既定では、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のプロセッサは無視された要素内のコンテンツを無視します。</span><span class="sxs-lookup"><span data-stu-id="4d65b-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="4d65b-118">`mc:ProcessContent`によって特定の要素を指定できます。また、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサは、無視された要素内のコンテンツを処理し続けます。</span><span class="sxs-lookup"><span data-stu-id="4d65b-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="4d65b-119">これは通常、コンテンツが複数のタグで入れ子になっている場合に使用されます。少なくとも1つは無視可能で、少なくとも1つは無視可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="4d65b-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="4d65b-120">属性では、複数のプレフィックスを指定できます。たとえば、`mc:ProcessContent="ignore:Element1 ignore:Element2"`のようにスペース区切り文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d65b-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="4d65b-121">`http://schemas.openxmlformats.org/markup-compatibility/2006` 名前空間は、SDK のこの領域内には記載されていない他の要素と属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d65b-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="4d65b-122">詳細については、「 [XML マークアップ互換性の仕様](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d65b-122">For more information, see [XML Markup Compatibility Specification](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d65b-123">参照</span><span class="sxs-lookup"><span data-stu-id="4d65b-123">See also</span></span>

- [<span data-ttu-id="4d65b-124">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="4d65b-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="4d65b-125">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="4d65b-125">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)

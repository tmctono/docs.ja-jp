---
title: mc:ProcessContent 属性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 619c3ffbc68c8c72ea9dd6545ab8da536380483b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206173"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="2a669-102">mc:ProcessContent 属性</span><span class="sxs-lookup"><span data-stu-id="2a669-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="2a669-103">[Mc: Ignorable 属性](mc-ignorable-attribute.md)を指定することが原因で、直接の親要素が[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサによって無視される場合でも、関連する親要素によって処理されるコンテンツを保持する要素を指定します。[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a669-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="2a669-104">属性`mc:ProcessContent`は、カスタム名前空間マッピング[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]とバージョン管理の両方で、マークアップ互換性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2a669-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2a669-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="2a669-105">XAML Attribute Usage</span></span>  
  
```  
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
  
## <a name="xaml-values"></a><span data-ttu-id="2a669-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="2a669-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a669-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="2a669-107">*ignorablePrefix*</span></span>|<span data-ttu-id="2a669-108">XML 1.0 仕様に従って、任意の有効なプレフィックス文字列。</span><span class="sxs-lookup"><span data-stu-id="2a669-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="2a669-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="2a669-109">*ignorableUri*</span></span>|<span data-ttu-id="2a669-110">XML 1.0 仕様に従って、名前空間を指定するための任意の有効な URI。</span><span class="sxs-lookup"><span data-stu-id="2a669-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="2a669-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="2a669-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="2a669-112">基になる型を解決でき[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ない場合に、プロセッサ実装によって無視される可能性がある要素。</span><span class="sxs-lookup"><span data-stu-id="2a669-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="2a669-113">*情報*</span><span class="sxs-lookup"><span data-stu-id="2a669-113">*[content]*</span></span>|<span data-ttu-id="2a669-114">*ThisElementCanBeIgnored*は無視としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="2a669-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="2a669-115">プロセッサがその要素を無視した場合、 *[content]* は*オブジェクト*によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="2a669-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a669-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a669-116">Remarks</span></span>  
 <span data-ttu-id="2a669-117">既定では、 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサは無視された要素内のコンテンツを無視します。</span><span class="sxs-lookup"><span data-stu-id="2a669-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="2a669-118">によって`mc:ProcessContent` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]特定の要素を指定することができ、プロセッサは無視された要素内のコンテンツを処理し続けます。</span><span class="sxs-lookup"><span data-stu-id="2a669-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="2a669-119">これは通常、コンテンツが複数のタグで入れ子になっている場合に使用されます。少なくとも1つは無視可能で、少なくとも1つは無視可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="2a669-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="2a669-120">属性では、スペース区切り記号 (など`mc:ProcessContent="ignore:Element1 ignore:Element2"`) を使用して、複数のプレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a669-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="2a669-121">名前`http://schemas.openxmlformats.org/markup-compatibility/2006`空間は、SDK のこの領域内には記載されていない他の要素と属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="2a669-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="2a669-122">詳細については、「 [XML マークアップ互換性の仕様](https://go.microsoft.com/fwlink/?LinkId=73824)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a669-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a669-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a669-123">See also</span></span>

- [<span data-ttu-id="2a669-124">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="2a669-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="2a669-125">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="2a669-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)

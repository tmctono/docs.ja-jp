---
title: mc:ProcessContent 属性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 865b1a3ccc30ff5efab4b08956bf7ba2bba4769c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017894"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="b3081-102">mc:ProcessContent 属性</span><span class="sxs-lookup"><span data-stu-id="b3081-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="b3081-103">指定します[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]要素もコンテンツがある、関連する親要素によって処理によって直接の親要素が無視される場合でも、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を指定するためのプロセッサ[mc: Ignorable 属性](mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="b3081-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="b3081-104">`mc:ProcessContent`属性は、カスタムの名前空間のマッピングとのマークアップの互換性をサポートしている[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]バージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="b3081-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b3081-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="b3081-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="b3081-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="b3081-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3081-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="b3081-107">*ignorablePrefix*</span></span>|<span data-ttu-id="b3081-108">有効なプレフィックスは、任意の文字列、XML 1.0 仕様に準拠します。</span><span class="sxs-lookup"><span data-stu-id="b3081-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="b3081-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="b3081-109">*ignorableUri*</span></span>|<span data-ttu-id="b3081-110">XML 1.0 仕様の名前空間を指定する有効な URI です。</span><span class="sxs-lookup"><span data-stu-id="b3081-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="b3081-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="b3081-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="b3081-112">要素を無視できる[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]プロセッサの実装を基になる型を解決できない場合。</span><span class="sxs-lookup"><span data-stu-id="b3081-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="b3081-113">*[コンテンツ]*</span><span class="sxs-lookup"><span data-stu-id="b3081-113">*[content]*</span></span>|<span data-ttu-id="b3081-114">*ThisElementCanBeIgnored* ignorable にマークされます。</span><span class="sxs-lookup"><span data-stu-id="b3081-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="b3081-115">プロセッサが、その要素を無視する場合は *[コンテンツ]* によって処理される*オブジェクト*します。</span><span class="sxs-lookup"><span data-stu-id="b3081-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3081-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3081-116">Remarks</span></span>  
 <span data-ttu-id="b3081-117">既定で、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサは、無視された要素内のコンテンツを無視します。</span><span class="sxs-lookup"><span data-stu-id="b3081-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="b3081-118">特定の要素を指定する`mc:ProcessContent`、および[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサが無視された要素内のコンテンツの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="b3081-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="b3081-119">これは通常、使用、コンテンツがうち少なくとも 1 つは無視でき、うち少なくとも 1 つは無視のいくつかのタグ内で入れ子になった場合。</span><span class="sxs-lookup"><span data-stu-id="b3081-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="b3081-120">たとえば、領域の区切り記号を使用して、属性で複数のプレフィックスを指定する場合があります:`mc:ProcessContent="ignore:Element1 ignore:Element2"`します。</span><span class="sxs-lookup"><span data-stu-id="b3081-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="b3081-121">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]名前空間は、他の要素とのこの領域内に記載されていない属性を定義、[!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b3081-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="b3081-122">詳細については、次を参照してください。 [XML マークアップ互換性仕様](https://go.microsoft.com/fwlink/?LinkId=73824)します。</span><span class="sxs-lookup"><span data-stu-id="b3081-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3081-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3081-123">See also</span></span>

- [<span data-ttu-id="b3081-124">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="b3081-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="b3081-125">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="b3081-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)

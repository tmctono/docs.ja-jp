---
title: ColorConvertedBitmap のマークアップ拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 7d14ddc6276b9dd7baee12e267e8af1250bc11ab
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582776"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="7867a-102">ColorConvertedBitmap のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="7867a-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="7867a-103">埋め込みプロファイルを持たないビットマップソースを指定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7867a-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="7867a-104">カラーコンテキスト/プロファイルは、イメージソース URI と同様に、URI によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="7867a-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7867a-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="7867a-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7867a-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="7867a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="7867a-107">プロファイルされていないビットマップの URI。</span><span class="sxs-lookup"><span data-stu-id="7867a-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="7867a-108">ソースプロファイル構成の URI。</span><span class="sxs-lookup"><span data-stu-id="7867a-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="7867a-109">送信先プロファイルの構成の URI</span><span class="sxs-lookup"><span data-stu-id="7867a-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7867a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7867a-110">Remarks</span></span>  
 <span data-ttu-id="7867a-111">このマークアップ拡張機能は、<xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A> などのイメージソースプロパティ値の関連するセットを埋めることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="7867a-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="7867a-112">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="7867a-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="7867a-113">`ColorConvertedBitmap` (または `ColorConvertedBitmapExtension`) をプロパティ要素の構文で使用することはできません。値を設定できるのは、拡張機能の識別子に続く文字列である初期コンストラクターの値に限られているためです。</span><span class="sxs-lookup"><span data-stu-id="7867a-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="7867a-114">`ColorConvertedBitmap` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="7867a-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="7867a-115">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="7867a-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="7867a-116">@No__t_0 内のすべてのマークアップ拡張機能は、属性構文で {および} 文字を使用します。これは、マークアップ拡張機能が属性を処理する必要があることを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサが認識する規則です。</span><span class="sxs-lookup"><span data-stu-id="7867a-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="7867a-117">詳細については、「[マークアップ拡張機能」および「WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7867a-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7867a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7867a-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="7867a-119">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="7867a-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="7867a-120">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="7867a-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)

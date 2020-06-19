---
title: ColorConvertedBitmap のマークアップ拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: a5b491723a036c1b1fd0bb61736e6f2ee53fbcd3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141225"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="535a2-102">ColorConvertedBitmap のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="535a2-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="535a2-103">埋め込みプロファイルのないビットマップ ソースを指定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="535a2-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="535a2-104">カラー コンテキストおよびプロファイルは、画像ソースの URI と同様に、URI によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="535a2-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="535a2-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="535a2-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a><span data-ttu-id="535a2-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="535a2-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="535a2-107">プロファイルにされていないビットマップの URI。</span><span class="sxs-lookup"><span data-stu-id="535a2-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="535a2-108">ソース プロファイル構成の URI。</span><span class="sxs-lookup"><span data-stu-id="535a2-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="535a2-109">ターゲット プロファイル構成の URI。</span><span class="sxs-lookup"><span data-stu-id="535a2-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="535a2-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="535a2-110">Remarks</span></span>  
 <span data-ttu-id="535a2-111">このマークアップ拡張では、<xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A> などの画像ソース プロパティ値の関連するセットを設定することが意図されています。</span><span class="sxs-lookup"><span data-stu-id="535a2-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="535a2-112">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="535a2-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="535a2-113">`ColorConvertedBitmap` (または `ColorConvertedBitmapExtension`) は、プロパティ要素の構文では使用できません。これは、最初のコンストラクターの値としてのみ値を設定できるだめです (拡張識別子の後の文字列)。</span><span class="sxs-lookup"><span data-stu-id="535a2-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="535a2-114">`ColorConvertedBitmap` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="535a2-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="535a2-115">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="535a2-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="535a2-116">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のすべてのマークアップ拡張では、それぞれの属性構文で { と } の 2 つの記号が使用されます。これは規約であり、これに従って [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサでは、マークアップ拡張で属性を処理する必要があることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="535a2-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="535a2-117">詳細については、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="535a2-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535a2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="535a2-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="535a2-119">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="535a2-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="535a2-120">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="535a2-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)

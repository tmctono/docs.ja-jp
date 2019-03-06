---
title: '方法: SystemFonts を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 5ed44da316ddee5ea3a83262f913da571bf75276
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378900"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="b1619-102">方法: SystemFonts を使用する</span><span class="sxs-lookup"><span data-stu-id="b1619-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="b1619-103">この例の静的なリソースを使用する方法を示しています、<xref:System.Windows.SystemFonts>クラスのスタイル設定やボタンをカスタマイズするためにします。</span><span class="sxs-lookup"><span data-stu-id="b1619-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1619-104">例</span><span class="sxs-lookup"><span data-stu-id="b1619-104">Example</span></span>  
 <span data-ttu-id="b1619-105">システム リソースは、システム設定と一貫性のあるビジュアルを作成できるようにするために、いくつかのシステムによって決定される値を、リソースおよびプロパティの両方として公開します。</span><span class="sxs-lookup"><span data-stu-id="b1619-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="b1619-106"><xref:System.Windows.SystemFonts> 静的プロパティは、および実行時にこれらの値を動的にアクセスするために使用するリソース キーを参照するプロパティとしての両方のシステム フォント値を含むクラスです。</span><span class="sxs-lookup"><span data-stu-id="b1619-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="b1619-107">たとえば、<xref:System.Windows.SystemFonts.CaptionFontFamily%2A>は、<xref:System.Windows.SystemFonts>値と<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>が対応するリソース キー。</span><span class="sxs-lookup"><span data-stu-id="b1619-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="b1619-108">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のメンバーを使用する<xref:System.Windows.SystemFonts>として静的プロパティまたは (キーとして静的プロパティの値) を含む動的リソース参照のいずれか。</span><span class="sxs-lookup"><span data-stu-id="b1619-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="b1619-109">アプリケーションの実行時にフォント メトリックを自動的に更新する場合は、動的リソース参照を使用します。それ以外の場合は、静的な値参照を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1619-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1619-110">リソース キーでは、プロパティ名に"Key"というサフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="b1619-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="b1619-111">次の例のプロパティを使用してアクセスする方法を示しています。<xref:System.Windows.SystemFonts>のスタイル設定やボタンをカスタマイズするために静的な値として。</span><span class="sxs-lookup"><span data-stu-id="b1619-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="b1619-112">このマークアップの例を割り当てます<xref:System.Windows.SystemFonts>をボタンの値。</span><span class="sxs-lookup"><span data-stu-id="b1619-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="b1619-113">値を使用する<xref:System.Windows.SystemFonts>コードでは、静的な値または動的リソース参照のいずれかを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1619-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="b1619-114">代わりのキー以外のプロパティを使用して、<xref:System.Windows.SystemFonts>クラス。</span><span class="sxs-lookup"><span data-stu-id="b1619-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="b1619-115">キー以外のプロパティは、実行時の動作の静的プロパティとして定義[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]によってホストされている、システムがリアルタイムでプロパティを再評価および値のシステムのユーザーによる変更が適切に考慮します。</span><span class="sxs-lookup"><span data-stu-id="b1619-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="b1619-116">次の例では、ボタンのフォント設定を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1619-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="b1619-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1619-117">See also</span></span>
- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="b1619-118">システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="b1619-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="b1619-119">SystemParameters を使用する</span><span class="sxs-lookup"><span data-stu-id="b1619-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="b1619-120">システム フォント キーを使用する</span><span class="sxs-lookup"><span data-stu-id="b1619-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="b1619-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b1619-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="b1619-122">x:Static のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="b1619-122">x:Static Markup Extension</span></span>](../../xaml-services/x-static-markup-extension.md)
- [<span data-ttu-id="b1619-123">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="b1619-123">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="b1619-124">DynamicResource マークアップ拡張</span><span class="sxs-lookup"><span data-stu-id="b1619-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)

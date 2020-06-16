---
title: '方法: SystemParameters を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 344fb54b48bcbf188b36a29d8205c21deff713c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001456"
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="92496-102">方法: SystemParameters を使用する</span><span class="sxs-lookup"><span data-stu-id="92496-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="92496-103">この例では、ボタンのスタイル設定やカスタマイズを行うために、<xref:System.Windows.SystemParameters> のプロパティにアクセスして使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="92496-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92496-104">例</span><span class="sxs-lookup"><span data-stu-id="92496-104">Example</span></span>  
 <span data-ttu-id="92496-105">システム リソースは、システム設定と一貫性のあるビジュアルを作成できるようにするために、いくつかのシステムに基づく設定をリソースとして公開します。</span><span class="sxs-lookup"><span data-stu-id="92496-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="92496-106"><xref:System.Windows.SystemParameters> は、システム パラメーター値のプロパティ、および値にバインドされるリソース キーの両方を含むクラスです。</span><span class="sxs-lookup"><span data-stu-id="92496-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="92496-107">たとえば、<xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> は <xref:System.Windows.SystemParameters> プロパティ値であり、<xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> は対応するリソース キーです。</span><span class="sxs-lookup"><span data-stu-id="92496-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="92496-108">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] では、<xref:System.Windows.SystemParameters> のメンバーを、静的プロパティの使用、または動的リソース参照 (静的プロパティ値をキーとして使用) として使用できます。</span><span class="sxs-lookup"><span data-stu-id="92496-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="92496-109">アプリケーションの実行時にシステムに基づく値を自動的に更新する場合は、動的リソース参照を使用します。それ以外の場合は、静的参照を使用します。</span><span class="sxs-lookup"><span data-stu-id="92496-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="92496-110">リソース キーのプロパティ名には、`Key` というサフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="92496-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="92496-111">次の例では、<xref:System.Windows.SystemParameters> の静的な値にアクセスして使用して、ボタンのスタイル設定またはカスタマイズを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="92496-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="92496-112">このマークアップの例では、ボタンに <xref:System.Windows.SystemParameters> 値を適用して、ボタンのサイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="92496-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="92496-113">コードで <xref:System.Windows.SystemParameters> の値を使用するために、静的参照または動的リソース参照を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92496-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="92496-114">代わりに、<xref:System.Windows.SystemParameters> クラスの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="92496-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="92496-115">キー以外のプロパティは静的プロパティとして定義されますが、システムでホストされた [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の実行時の動作では、リアルタイムでプロパティが再評価され、ユーザーによるシステム値の変更が正しく反映されます。</span><span class="sxs-lookup"><span data-stu-id="92496-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="92496-116">次の例では、<xref:System.Windows.SystemParameters> 値を使用して、ボタンの幅と高さを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="92496-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="92496-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="92496-117">See also</span></span>

- <xref:System.Windows.SystemParameters>
- [<span data-ttu-id="92496-118">システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="92496-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="92496-119">SystemFonts を使用する</span><span class="sxs-lookup"><span data-stu-id="92496-119">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="92496-120">システム パラメーター キーを使用する</span><span class="sxs-lookup"><span data-stu-id="92496-120">Use System Parameters Keys</span></span>](how-to-use-system-parameters-keys.md)
- [<span data-ttu-id="92496-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="92496-121">How-to Topics</span></span>](resources-how-to-topics.md)

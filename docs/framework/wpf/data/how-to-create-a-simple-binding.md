---
title: '方法 : 簡単なバインディングを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453500"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="5db84-102">方法 : 簡単なバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="5db84-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="5db84-103">この例では、単純な <xref:System.Windows.Data.Binding>を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5db84-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db84-104">例</span><span class="sxs-lookup"><span data-stu-id="5db84-104">Example</span></span>  
 <span data-ttu-id="5db84-105">この例では、`PersonName`という名前の文字列プロパティを持つ `Person` オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="5db84-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="5db84-106">`Person` オブジェクトは、`SDKSample`と呼ばれる名前空間で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5db84-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="5db84-107">次の例の `<src>` 要素を含む強調表示された行では、`Joe`の `PersonName` プロパティ値を使用して `Person` オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="5db84-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="5db84-108">これは `Resources` セクションで行い、`x:Key`を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5db84-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="5db84-109">`<TextBlock>` 要素を含む強調表示された行は、<xref:System.Windows.Controls.TextBlock> コントロールを `PersonName` プロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="5db84-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="5db84-110">その結果、<xref:System.Windows.Controls.TextBlock> に "Joe" という値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5db84-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db84-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5db84-111">See also</span></span>

- [<span data-ttu-id="5db84-112">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="5db84-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5db84-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="5db84-113">How-to Topics</span></span>](data-binding-how-to-topics.md)

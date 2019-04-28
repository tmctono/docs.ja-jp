---
title: '方法: 簡単なバインディングを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931568"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="8c963-102">方法: 簡単なバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="8c963-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="8c963-103">この例、単純なを作成する方法を示します<xref:System.Windows.Data.Binding>します。</span><span class="sxs-lookup"><span data-stu-id="8c963-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c963-104">例</span><span class="sxs-lookup"><span data-stu-id="8c963-104">Example</span></span>  
 <span data-ttu-id="8c963-105">この例である、`Person`という名前の文字列プロパティを持つオブジェクト`PersonName`します。</span><span class="sxs-lookup"><span data-stu-id="8c963-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="8c963-106">`Person`という名前空間でオブジェクトが定義されている`SDKSample`します。</span><span class="sxs-lookup"><span data-stu-id="8c963-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="8c963-107">強調表示された行を含む、`<src>`次の例では、内の要素をインスタンス化、`Person`オブジェクトを`PersonName`プロパティの値`Joe`します。</span><span class="sxs-lookup"><span data-stu-id="8c963-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="8c963-108">これを行う、`Resources`セクションし、割り当てられている、`x:Key`します。</span><span class="sxs-lookup"><span data-stu-id="8c963-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="8c963-109">強調表示された行を含む、`<TextBlock>`要素にバインドし、<xref:System.Windows.Controls.TextBlock>への制御、`PersonName`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8c963-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="8c963-110">結果として、 <xref:System.Windows.Controls.TextBlock> "Joe"の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c963-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c963-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c963-111">See also</span></span>

- [<span data-ttu-id="8c963-112">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="8c963-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="8c963-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8c963-113">How-to Topics</span></span>](data-binding-how-to-topics.md)

---
title: '方法: 簡単なバインディングを作成する'
description: Windows Presentation Foundation (WPF) で、この操作方法の例を使用して、アプリケーションの簡単なバインディングを作成します。
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618702"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="4f9d6-103">方法: 簡単なバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="4f9d6-103">How to: Create a Simple Binding</span></span>
<span data-ttu-id="4f9d6-104">この例では、簡単な <xref:System.Windows.Data.Binding> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-104">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f9d6-105">例</span><span class="sxs-lookup"><span data-stu-id="4f9d6-105">Example</span></span>  
 <span data-ttu-id="4f9d6-106">この例では、`PersonName` という名前の文字列プロパティを持つ `Person` オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-106">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="4f9d6-107">`Person` オブジェクトは `SDKSample` という名前空間で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="4f9d6-108">次の例の `<src>` 要素を含む強調表示された行では、`PersonName` プロパティの値が `Joe` である `Person` オブジェクトがインスタンス化されています。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-108">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="4f9d6-109">これは `Resources` セクションで行われ、`x:Key` が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-109">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="4f9d6-110">`<TextBlock>` 要素を含む強調表示された行では、<xref:System.Windows.Controls.TextBlock> コントロールが `PersonName` プロパティにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-110">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="4f9d6-111">その結果、<xref:System.Windows.Controls.TextBlock> に "Joe" という値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f9d6-111">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9d6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f9d6-112">See also</span></span>

- [<span data-ttu-id="4f9d6-113">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="4f9d6-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="4f9d6-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="4f9d6-114">How-to Topics</span></span>](data-binding-how-to-topics.md)

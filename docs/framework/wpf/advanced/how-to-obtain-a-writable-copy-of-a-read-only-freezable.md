---
title: '方法: 読み取り専用の Freezable の書き込み可能なコピーを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206474"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="200f9-102">方法: 読み取り専用の Freezable の書き込み可能なコピーを取得する</span><span class="sxs-lookup"><span data-stu-id="200f9-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="200f9-103">この例は、使用する方法を示します、<xref:System.Windows.Freezable.Clone%2A>読み取り専用の書き込み可能なコピーを作成するメソッドを<xref:System.Windows.Freezable>します。</span><span class="sxs-lookup"><span data-stu-id="200f9-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="200f9-104">後に、<xref:System.Windows.Freezable>オブジェクトがマークされている読み取り専用 (「固定」)、として、それを変更できません。</span><span class="sxs-lookup"><span data-stu-id="200f9-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="200f9-105">ただし、使用することができます、<xref:System.Windows.Freezable.Clone%2A>固定されたオブジェクトの変更可能な複製を作成します。</span><span class="sxs-lookup"><span data-stu-id="200f9-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="200f9-106">例</span><span class="sxs-lookup"><span data-stu-id="200f9-106">Example</span></span>  
 <span data-ttu-id="200f9-107">次の例は、固定の変更可能な複製を作成<xref:System.Windows.Media.SolidColorBrush>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="200f9-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="200f9-108">詳細については<xref:System.Windows.Freezable>、オブジェクトを参照してください、 [Freezable オブジェクトの概要](freezable-objects-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="200f9-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200f9-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="200f9-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="200f9-110">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="200f9-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="200f9-111">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="200f9-111">How-to Topics</span></span>](base-elements-how-to-topics.md)

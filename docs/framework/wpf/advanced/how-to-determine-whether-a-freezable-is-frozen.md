---
title: '方法: Freezable が固定されているかどうかを判別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362514"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="2d7b8-102">方法: Freezable が固定されているかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="2d7b8-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="2d7b8-103">この例を確認する方法を示して かどうかを<xref:System.Windows.Freezable>オブジェクトが固定されています。</span><span class="sxs-lookup"><span data-stu-id="2d7b8-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="2d7b8-104">固定された変更を行う場合<xref:System.Windows.Freezable>オブジェクトがスローされます、<xref:System.InvalidOperationException>します。</span><span class="sxs-lookup"><span data-stu-id="2d7b8-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="2d7b8-105">この例外をスローすることを避けるため、使用、<xref:System.Windows.Freezable.IsFrozen%2A>のプロパティ、<xref:System.Windows.Freezable>が固定されているかどうかを判断するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d7b8-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d7b8-106">例</span><span class="sxs-lookup"><span data-stu-id="2d7b8-106">Example</span></span>  
 <span data-ttu-id="2d7b8-107">次の例では、フリーズ、<xref:System.Windows.Media.SolidColorBrush>を使用してテストし、その、<xref:System.Windows.Freezable.IsFrozen%2A>が固定されているかどうかを決定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2d7b8-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="2d7b8-108">詳細については<xref:System.Windows.Freezable>、オブジェクトを参照してください、 [Freezable オブジェクトの概要](freezable-objects-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d7b8-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7b8-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d7b8-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="2d7b8-110">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="2d7b8-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="2d7b8-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="2d7b8-111">How-to Topics</span></span>](base-elements-how-to-topics.md)

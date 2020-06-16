---
title: '方法: Freezable が固定されているかどうかを判別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776234"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="f25b7-102">方法: Freezable が固定されているかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="f25b7-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="f25b7-103">この例では、<xref:System.Windows.Freezable> オブジェクトが固定されているかどうかを判別する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f25b7-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="f25b7-104">固定された <xref:System.Windows.Freezable> オブジェクトを変更しようとすると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f25b7-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="f25b7-105">この例外がスローされないようにするには、<xref:System.Windows.Freezable> オブジェクトの <xref:System.Windows.Freezable.IsFrozen%2A> プロパティを使用して、固定されているかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="f25b7-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f25b7-106">例</span><span class="sxs-lookup"><span data-stu-id="f25b7-106">Example</span></span>  
 <span data-ttu-id="f25b7-107">次の例では、<xref:System.Windows.Media.SolidColorBrush> を固定し、<xref:System.Windows.Freezable.IsFrozen%2A> プロパティを使用してテストし、固定されているかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="f25b7-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="f25b7-108"><xref:System.Windows.Freezable> オブジェクトの詳細については、「[Freezable オブジェクトの概要](freezable-objects-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f25b7-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25b7-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="f25b7-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="f25b7-110">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="f25b7-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="f25b7-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f25b7-111">How-to Topics</span></span>](base-elements-how-to-topics.md)

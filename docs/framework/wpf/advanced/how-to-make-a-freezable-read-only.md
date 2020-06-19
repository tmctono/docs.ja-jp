---
title: '方法: Freezable を読み取り専用にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460071"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="08ba9-102">方法: Freezable を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="08ba9-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="08ba9-103">この例では、<xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出して <xref:System.Windows.Freezable> を読み取り専用にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="08ba9-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="08ba9-104">オブジェクトについて次のいずれかの条件が `true` の場合、<xref:System.Windows.Freezable> オブジェクトを凍結することはできません。</span><span class="sxs-lookup"><span data-stu-id="08ba9-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="08ba9-105">アニメーション化されたプロパティまたはデータ バインドされたプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="08ba9-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="08ba9-106">動的リソースによって設定されるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="08ba9-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="08ba9-107">動的リソースの詳細については、[XAML リソース](../../../desktop-wpf/fundamentals/xaml-resources-define.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08ba9-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="08ba9-108">凍結できない <xref:System.Windows.Freezable> サブオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="08ba9-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="08ba9-109"><xref:System.Windows.Freezable> オブジェクトに対して、これらの条件が `false` であり、このオブジェクトを変更する予定がない場合は、パフォーマンスを向上させるために凍結させることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="08ba9-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08ba9-110">例</span><span class="sxs-lookup"><span data-stu-id="08ba9-110">Example</span></span>  
 <span data-ttu-id="08ba9-111">次の例では、<xref:System.Windows.Freezable> オブジェクトの型である <xref:System.Windows.Media.SolidColorBrush> を凍結します。</span><span class="sxs-lookup"><span data-stu-id="08ba9-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="08ba9-112"><xref:System.Windows.Freezable> オブジェクトの詳細については、「[Freezable オブジェクトの概要](freezable-objects-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08ba9-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ba9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="08ba9-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="08ba9-114">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="08ba9-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="08ba9-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="08ba9-115">How-to Topics</span></span>](base-elements-how-to-topics.md)

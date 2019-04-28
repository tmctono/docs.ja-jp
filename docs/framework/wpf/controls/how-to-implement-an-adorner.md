---
title: '方法: 装飾を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770982"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="3398a-102">方法: 装飾を実装する</span><span class="sxs-lookup"><span data-stu-id="3398a-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="3398a-103">この例では、最小限の装飾の実装を示します。</span><span class="sxs-lookup"><span data-stu-id="3398a-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="3398a-104">実装についてのメモ</span><span class="sxs-lookup"><span data-stu-id="3398a-104">Notes for Implementers</span></span>  
 <span data-ttu-id="3398a-105">装飾自体にはレンダリング動作が備わっていないので、装飾のレンダリングは装飾の実装側の責任で行う必要がある点に、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="3398a-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="3398a-106">一般的なレンダリングの動作を実装する方法は、オーバーライドする、<xref:System.Windows.UIElement.OnRender%2A>メソッドと 1 つ以上を使用して<xref:System.Windows.Media.DrawingContext>(この例で示す) のように、必要に応じて、装飾のビジュアルを表示するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3398a-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3398a-107">例</span><span class="sxs-lookup"><span data-stu-id="3398a-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3398a-108">説明</span><span class="sxs-lookup"><span data-stu-id="3398a-108">Description</span></span>  
 <span data-ttu-id="3398a-109">抽象から継承するクラスを実装することで、カスタム装飾が作成された<xref:System.Windows.Documents.Adorner>クラス。</span><span class="sxs-lookup"><span data-stu-id="3398a-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="3398a-110">例を装飾するだけのものの角に丸みを<xref:System.Windows.UIElement>オーバーライドすることで円で、<xref:System.Windows.UIElement.OnRender%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="3398a-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3398a-111">コード</span><span class="sxs-lookup"><span data-stu-id="3398a-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="3398a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3398a-112">See also</span></span>

- [<span data-ttu-id="3398a-113">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="3398a-113">Adorners Overview</span></span>](adorners-overview.md)

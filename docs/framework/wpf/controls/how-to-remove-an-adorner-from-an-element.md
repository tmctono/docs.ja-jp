---
title: '方法: 要素から装飾を削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212402"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="079c8-102">方法: 要素から装飾を削除する</span><span class="sxs-lookup"><span data-stu-id="079c8-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="079c8-103">この例は、プログラムで指定した特定の装飾を削除する方法を示しています。<xref:System.Windows.UIElement>します。</span><span class="sxs-lookup"><span data-stu-id="079c8-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="079c8-104">例</span><span class="sxs-lookup"><span data-stu-id="079c8-104">Example</span></span>  
 <span data-ttu-id="079c8-105">この簡潔なコード例は、によって返される装飾の配列の最初のガイドを削除します<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>します。</span><span class="sxs-lookup"><span data-stu-id="079c8-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="079c8-106">この例の発生時に、装飾を取得する、<xref:System.Windows.UIElement>という*myTextBox*します。</span><span class="sxs-lookup"><span data-stu-id="079c8-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="079c8-107">呼び出しで、要素が指定されている場合<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>、装飾を持たない`null`が返されます。</span><span class="sxs-lookup"><span data-stu-id="079c8-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="079c8-108">このコードは明示的に null の配列をチェックし、アプリケーションに最適に比較的一般的な null 配列が必要な場合は、します。</span><span class="sxs-lookup"><span data-stu-id="079c8-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="079c8-109">例</span><span class="sxs-lookup"><span data-stu-id="079c8-109">Example</span></span>  
 <span data-ttu-id="079c8-110">この要約のコード例は、機能的には、前述の詳細な例です。</span><span class="sxs-lookup"><span data-stu-id="079c8-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="079c8-111">このコードで明示的に確認、null 配列のできないできるようにする、<xref:System.NullReferenceException>例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="079c8-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="079c8-112">このコードは、null 配列のまれなことが必要です、アプリケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="079c8-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="079c8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="079c8-113">See also</span></span>

- [<span data-ttu-id="079c8-114">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="079c8-114">Adorners Overview</span></span>](adorners-overview.md)

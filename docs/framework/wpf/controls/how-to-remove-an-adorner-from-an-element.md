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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770761"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="d7f1d-102">方法: 要素から装飾を削除する</span><span class="sxs-lookup"><span data-stu-id="d7f1d-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="d7f1d-103">この例では、指定された <xref:System.Windows.UIElement> から特定の装飾をプログラムで削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7f1d-104">例</span><span class="sxs-lookup"><span data-stu-id="d7f1d-104">Example</span></span>  
 <span data-ttu-id="d7f1d-105">この詳細なコード例では、<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> によって返される装飾の配列に含まれる最初の装飾を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="d7f1d-106">この例では、*myTextBox* という名前の <xref:System.Windows.UIElement> の装飾を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="d7f1d-107"><xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> の呼び出しで指定された要素に装飾がない場合、`null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="d7f1d-108">このコードによって、Null 配列が明示的にチェックされます。これは、Null 配列が比較的一般的であると予想されるアプリケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="d7f1d-109">例</span><span class="sxs-lookup"><span data-stu-id="d7f1d-109">Example</span></span>  
 <span data-ttu-id="d7f1d-110">この簡約されたコード例は、上記の詳細な例と機能的には同等です。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="d7f1d-111">このコードでは、Null 配列が明示的にチェックされないため、<xref:System.NullReferenceException> の例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="d7f1d-112">このコードは、Null 配列がまれであると予想されるアプリケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="d7f1d-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="d7f1d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7f1d-113">See also</span></span>

- [<span data-ttu-id="d7f1d-114">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="d7f1d-114">Adorners Overview</span></span>](adorners-overview.md)

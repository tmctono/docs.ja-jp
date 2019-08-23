---
title: UI オートメーションを使用した、テキスト ボックスへのコンテンツの追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: fdc52d0b94ce500b6560b60419d409f5cbd73b55
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932653"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="e68f4-102">UI オートメーションを使用した、テキスト ボックスへのコンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="e68f4-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="e68f4-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="e68f4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e68f4-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="e68f4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e68f4-105">このトピックでは、を使用[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]して1行のテキストボックスにテキストを挿入する方法を示すコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="e68f4-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="e68f4-106">複数行およびリッチテキストコントロール[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]に対しては、を適用できない代替の方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e68f4-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="e68f4-107">比較のために、この例では、Win32 メソッドを使用して同じ結果を実現する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="e68f4-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e68f4-108">例</span><span class="sxs-lookup"><span data-stu-id="e68f4-108">Example</span></span>  
 <span data-ttu-id="e68f4-109">次の例では、対象アプリケーションのテキストコントロールのシーケンスをステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="e68f4-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="e68f4-110">各テキストコントロールは、 <xref:System.Windows.Automation.ValuePattern> <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>メソッドを使用してオブジェクトを取得できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="e68f4-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="e68f4-111">テキストコントロールでがサポート<xref:System.Windows.Automation.ValuePattern>されている場合<xref:System.Windows.Automation.ValuePattern.SetValue%2A> 、メソッドを使用して、ユーザー定義の文字列をテキストコントロールに挿入します。</span><span class="sxs-lookup"><span data-stu-id="e68f4-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="e68f4-112">それ以外の<xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>場合は、メソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e68f4-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="e68f4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e68f4-113">See also</span></span>

- <span data-ttu-id="e68f4-114">[TextPattern の挿入テキストのサンプル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e68f4-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>

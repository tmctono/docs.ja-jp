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
ms.openlocfilehash: 9183aecdc47d54aef26d5cdca8ea11d8398be732
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61610076"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="00117-102">UI オートメーションを使用した、テキスト ボックスへのコンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="00117-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="00117-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="00117-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="00117-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="00117-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="00117-105">このトピックを使用する方法を示すコード例が含まれています。[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]に 1 行のテキスト ボックスにテキストを挿入します。</span><span class="sxs-lookup"><span data-stu-id="00117-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="00117-106">複数行、およびリッチ テキスト コントロールの別の方法が提供されている場所[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]は適用されません。</span><span class="sxs-lookup"><span data-stu-id="00117-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="00117-107">比較のために、この例は Win32 メソッドを使用して同じ結果を達成する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="00117-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00117-108">例</span><span class="sxs-lookup"><span data-stu-id="00117-108">Example</span></span>  
 <span data-ttu-id="00117-109">ターゲット アプリケーション内のテキスト コントロールの順序で次の例の手順。</span><span class="sxs-lookup"><span data-stu-id="00117-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="00117-110">各テキスト コントロールがかどうかをテストする<xref:System.Windows.Automation.ValuePattern>を使用してオブジェクトを取得できる、<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="00117-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="00117-111">テキスト コントロールはサポートしている場合<xref:System.Windows.Automation.ValuePattern>、<xref:System.Windows.Automation.ValuePattern.SetValue%2A>テキスト コントロールにユーザー定義の文字列を挿入するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="00117-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="00117-112">それ以外の場合、<xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="00117-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="00117-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="00117-113">See also</span></span>

- <span data-ttu-id="00117-114">[TextPattern の挿入テキスト サンプル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="00117-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>

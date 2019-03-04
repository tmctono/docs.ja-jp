---
title: '方法: Visual Basic で接続ステータスをチェックする'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: bb3d5751ae7d88af05c2a77e9b64f9cb28179a35
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973016"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="5b5df-102">方法: Visual Basic で接続ステータスをチェックする</span><span class="sxs-lookup"><span data-stu-id="5b5df-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="5b5df-103">正常に動作しているネットワーク接続またはインターネット接続がコンピューターにあるかどうかは、<xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> プロパティを使って調べることができます。</span><span class="sxs-lookup"><span data-stu-id="5b5df-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="5b5df-104">正常に動作している接続がコンピューターにあるかどうかを調べるには</span><span class="sxs-lookup"><span data-stu-id="5b5df-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="5b5df-105">`IsAvailable` プロパティが `True` であるか `False` であるかを調べます。</span><span class="sxs-lookup"><span data-stu-id="5b5df-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="5b5df-106">このプロパティのステータスを調べて報告するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b5df-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="5b5df-107">このコード例は、IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="5b5df-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="5b5df-108">コード スニペット ピッカーでは、これは **[接続とネットワーク]** にあります。</span><span class="sxs-lookup"><span data-stu-id="5b5df-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="5b5df-109">詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b5df-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5df-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b5df-110">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>

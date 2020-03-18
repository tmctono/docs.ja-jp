---
title: '方法 : 接続ステータスをチェックする'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: 89ef431759dac25bd213fd954db0712ad95434b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345879"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="06ad3-102">方法 : Visual Basic で接続ステータスをチェックする</span><span class="sxs-lookup"><span data-stu-id="06ad3-102">How to: Check Connection Status in Visual Basic</span></span>

<span data-ttu-id="06ad3-103">正常に動作しているネットワーク接続またはインターネット接続がコンピューターにあるかどうかは、<xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> プロパティを使って調べることができます。</span><span class="sxs-lookup"><span data-stu-id="06ad3-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="06ad3-104">正常に動作している接続がコンピューターにあるかどうかを調べるには</span><span class="sxs-lookup"><span data-stu-id="06ad3-104">To check whether a computer has a working connection</span></span>  
  
- <span data-ttu-id="06ad3-105">`IsAvailable` プロパティが `True` であるか `False` であるかを調べます。</span><span class="sxs-lookup"><span data-stu-id="06ad3-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="06ad3-106">このプロパティのステータスを調べて報告するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="06ad3-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="06ad3-107">このコード例は IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="06ad3-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="06ad3-108">コード スニペット ピッカーでは、これは **[接続とネットワーク]** にあります。</span><span class="sxs-lookup"><span data-stu-id="06ad3-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="06ad3-109">詳細については、「 [Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06ad3-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ad3-110">参照</span><span class="sxs-lookup"><span data-stu-id="06ad3-110">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>

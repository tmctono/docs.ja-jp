---
title: '方法: Visual Basic で接続ステータスをチェックする'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: 1a03b181c2e363c3380c4f9858b629713641f2c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620676"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="43e85-102">方法: Visual Basic で接続ステータスをチェックする</span><span class="sxs-lookup"><span data-stu-id="43e85-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="43e85-103">正常に動作しているネットワーク接続またはインターネット接続がコンピューターにあるかどうかは、<xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> プロパティを使って調べることができます。</span><span class="sxs-lookup"><span data-stu-id="43e85-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="43e85-104">正常に動作している接続がコンピューターにあるかどうかを調べるには</span><span class="sxs-lookup"><span data-stu-id="43e85-104">To check whether a computer has a working connection</span></span>  
  
- <span data-ttu-id="43e85-105">`IsAvailable` プロパティが `True` であるか `False` であるかを調べます。</span><span class="sxs-lookup"><span data-stu-id="43e85-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="43e85-106">このプロパティのステータスを調べて報告するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="43e85-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="43e85-107">このコード例は、IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="43e85-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="43e85-108">コード スニペット ピッカーでは、これは **[接続とネットワーク]** にあります。</span><span class="sxs-lookup"><span data-stu-id="43e85-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="43e85-109">詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43e85-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e85-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="43e85-110">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>

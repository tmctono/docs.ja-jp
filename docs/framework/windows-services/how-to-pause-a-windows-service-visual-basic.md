---
title: '方法: Windows サービスを一時中断する (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 166eda4a9348188fa6e5048fd3ce41645cde4816
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053599"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="358b4-102">方法: Windows サービスを一時中断する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="358b4-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="358b4-103">この例では、<xref:System.ServiceProcess.ServiceController> コンポーネントを使って、ローカル コンピューター上の IIS 管理サービスを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="358b4-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="358b4-104">例</span><span class="sxs-lookup"><span data-stu-id="358b4-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="358b4-105">このコード例は、IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="358b4-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="358b4-106">コード スニペット ピッカーでは、これは **[Windows オペレーティング システム] > [Windows サービス]** に配置されます。</span><span class="sxs-lookup"><span data-stu-id="358b4-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="358b4-107">詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="358b4-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="358b4-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="358b4-108">Compiling the Code</span></span>  
 <span data-ttu-id="358b4-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="358b4-109">This example requires:</span></span>  
  
- <span data-ttu-id="358b4-110">System.serviceprocess.dll へのプロジェクト参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="358b4-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="358b4-111"><xref:System.ServiceProcess> 名前空間のメンバーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="358b4-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="358b4-112">コード内でメンバー名を完全修飾していない場合は、`Imports` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="358b4-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="358b4-113">詳細については、「[Imports ステートメント (.NET 名前空間および型)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="358b4-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="358b4-114">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="358b4-114">Robust Programming</span></span>  
 <span data-ttu-id="358b4-115"><xref:System.ServiceProcess.ServiceController> クラスの <xref:System.ServiceProcess.ServiceController.MachineName%2A> プロパティは、既定ではローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="358b4-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="358b4-116">別のコンピューター上の Windows サービスを参照するには、<xref:System.ServiceProcess.ServiceController.MachineName%2A> プロパティをそのコンピューターの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="358b4-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="358b4-117">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="358b4-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="358b4-118">サービスを一時停止できません。</span><span class="sxs-lookup"><span data-stu-id="358b4-118">The service cannot be paused.</span></span> <span data-ttu-id="358b4-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="358b4-119">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="358b4-120">システム API にアクセス中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="358b4-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="358b4-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="358b4-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="358b4-122">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="358b4-122">.NET Framework Security</span></span>  
 <span data-ttu-id="358b4-123">コンピューター上のサービスの制御は、<xref:System.ServiceProcess.ServiceControllerPermissionAccess> を使って <xref:System.ServiceProcess.ServiceControllerPermission> のアクセス許可を設定することにより制限できます。</span><span class="sxs-lookup"><span data-stu-id="358b4-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="358b4-124">サービス情報へのアクセスは、<xref:System.Security.Permissions.PermissionState> を使って <xref:System.Security.Permissions.SecurityPermission> のアクセス許可を設定することにより制限できます。</span><span class="sxs-lookup"><span data-stu-id="358b4-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358b4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="358b4-125">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="358b4-126">方法: Windows サービスを続行する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="358b4-126">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)

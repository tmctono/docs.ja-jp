---
title: '方法: Windows サービスを続行する (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: 160d1b5f0604cff96549c9d94dc5d8ddc7e39f09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217160"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="5c708-102">方法: Windows サービスを続行する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c708-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="5c708-103">この例では、<xref:System.ServiceProcess.ServiceController> コンポーネントを使って、ローカル コンピューター上の IIS 管理サービスを続行します。</span><span class="sxs-lookup"><span data-stu-id="5c708-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c708-104">例</span><span class="sxs-lookup"><span data-stu-id="5c708-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="5c708-105">このコード例は、IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="5c708-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="5c708-106">コード スニペット ピッカーでは、これは **[Windows オペレーティング システム] > [Windows サービス]** に配置されます。</span><span class="sxs-lookup"><span data-stu-id="5c708-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="5c708-107">詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c708-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c708-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5c708-108">Compiling the Code</span></span>  
 <span data-ttu-id="5c708-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5c708-109">This example requires:</span></span>  
  
-   <span data-ttu-id="5c708-110">System.serviceprocess.dll へのプロジェクト参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c708-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="5c708-111"><xref:System.ServiceProcess> 名前空間のメンバーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="5c708-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="5c708-112">コード内でメンバー名を完全修飾していない場合は、`Imports` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c708-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="5c708-113">詳細については、「[Imports ステートメント (.NET 名前空間および型)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c708-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5c708-114">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="5c708-114">Robust Programming</span></span>  
 <span data-ttu-id="5c708-115"><xref:System.ServiceProcess.ServiceController> クラスの <xref:System.ServiceProcess.ServiceController.MachineName%2A> プロパティは、既定ではローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="5c708-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="5c708-116">別のコンピューター上の Windows サービスを参照するには、<xref:System.ServiceProcess.ServiceController.MachineName%2A> プロパティをそのコンピューターの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="5c708-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="5c708-117">サービス コントローラーの状態が <xref:System.ServiceProcess.ServiceControllerStatus.Paused> になるまで、サービスに対して <xref:System.ServiceProcess.ServiceController.Continue%2A> メソッド呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5c708-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="5c708-118">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c708-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="5c708-119">サービスを再開できません。</span><span class="sxs-lookup"><span data-stu-id="5c708-119">The service cannot be resumed.</span></span> <span data-ttu-id="5c708-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="5c708-120">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="5c708-121">システム API にアクセス中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5c708-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="5c708-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="5c708-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5c708-123">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="5c708-123">.NET Framework Security</span></span>  
 <span data-ttu-id="5c708-124">コンピューター上のサービスの制御は、<xref:System.ServiceProcess.ServiceControllerPermissionAccess> 列挙型を使って <xref:System.ServiceProcess.ServiceControllerPermission> クラスのアクセス許可を設定することにより制限できます。</span><span class="sxs-lookup"><span data-stu-id="5c708-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="5c708-125">サービス情報へのアクセスは、<xref:System.Security.Permissions.PermissionState> 列挙型を使って <xref:System.Security.Permissions.SecurityPermission> クラスのアクセス許可を設定することにより制限できます。</span><span class="sxs-lookup"><span data-stu-id="5c708-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c708-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c708-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="5c708-127">方法: Windows サービスを一時中断する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c708-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)

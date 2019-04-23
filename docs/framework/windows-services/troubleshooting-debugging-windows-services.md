---
title: トラブルシューティング:Windows サービスをデバッグする場合
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: 0552fc005a25e83065bb44e425770f9cef84f71b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082582"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="677c5-102">トラブルシューティング:Windows サービスをデバッグする場合</span><span class="sxs-lookup"><span data-stu-id="677c5-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="677c5-103">Windows サービス アプリケーションをデバッグするとき、サービスと **Windows Service Manager** の間でやり取りが行われます。</span><span class="sxs-lookup"><span data-stu-id="677c5-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="677c5-104">**Service Manager** は <xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドを呼び出してサービスを開始した後、<xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドから戻るのを 30 秒間待ちます。</span><span class="sxs-lookup"><span data-stu-id="677c5-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="677c5-105">この時間内にメソッドから戻らない場合、Manager はサービスを開始できないというエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="677c5-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="677c5-106"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドについて「[方法:Windows サービス アプリケーションをデバッグする](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)」の説明に従ってデバッグする場合、この 30 秒間のことを認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="677c5-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="677c5-107"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドにブレークポイントを設定し、30 秒以内にメソッドを最後までステップ実行しないと、Manager はサービスを開始しません。</span><span class="sxs-lookup"><span data-stu-id="677c5-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="677c5-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="677c5-108">See also</span></span>

- [<span data-ttu-id="677c5-109">方法: Windows サービス アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="677c5-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="677c5-110">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="677c5-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)

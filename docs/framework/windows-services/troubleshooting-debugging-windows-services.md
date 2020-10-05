---
title: トラブルシューティング:Windows サービスをデバッグする場合
description: Windows サービスのデバッグを開始します。 Windows サービス アプリケーションをデバッグするとき、サービスと Windows Service Manager の間でやり取りが行われます。
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
ms.openlocfilehash: 5846692fa0d90a62dd569253abbd81aa63b5798d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608895"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="a40fb-104">トラブルシューティング:Windows サービスをデバッグする場合</span><span class="sxs-lookup"><span data-stu-id="a40fb-104">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="a40fb-105">Windows サービス アプリケーションをデバッグするとき、サービスと **Windows Service Manager** の間でやり取りが行われます。</span><span class="sxs-lookup"><span data-stu-id="a40fb-105">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="a40fb-106">**Service Manager** は <xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドを呼び出してサービスを開始した後、<xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドから戻るのを 30 秒間待ちます。</span><span class="sxs-lookup"><span data-stu-id="a40fb-106">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="a40fb-107">この時間内にメソッドから戻らない場合、Manager はサービスを開始できないというエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="a40fb-107">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="a40fb-108"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドについて「[方法:Windows サービス アプリケーションをデバッグする](how-to-debug-windows-service-applications.md)」の説明に従ってデバッグする場合、この 30 秒間のことを認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a40fb-108">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="a40fb-109"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドにブレークポイントを設定し、30 秒以内にメソッドを最後までステップ実行しないと、Manager はサービスを開始しません。</span><span class="sxs-lookup"><span data-stu-id="a40fb-109">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40fb-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a40fb-110">See also</span></span>

- [<span data-ttu-id="a40fb-111">方法: Windows サービス アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="a40fb-111">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="a40fb-112">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="a40fb-112">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

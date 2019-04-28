---
title: WebBrowser セキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 1e658c25ea19f966ac67402c6f3c7693c784d029
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792120"
---
# <a name="webbrowser-security"></a><span data-ttu-id="3149b-102">WebBrowser セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3149b-102">WebBrowser Security</span></span>
<span data-ttu-id="3149b-103"><xref:System.Windows.Forms.WebBrowser>コントロールがデザインされた、完全な信頼のみで機能します。</span><span class="sxs-lookup"><span data-stu-id="3149b-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="3149b-104">コントロールに表示される HTML コンテンツでは、外部の Web サーバーから取得でき、スクリプトまたは Web コントロールの形式でアンマネージ コードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3149b-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="3149b-105">使用する場合、<xref:System.Windows.Forms.WebBrowser>この状況では、コントロール内のコントロールは Internet Explorer である場合は、管理ですがより安全性が<xref:System.Windows.Forms.WebBrowser>コントロールが実行されているからこのようなアンマネージ コードを妨げません。</span><span class="sxs-lookup"><span data-stu-id="3149b-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="3149b-106">基になる ActiveX に関連するセキュリティ問題の詳細については`WebBrowser`コントロールを参照してください[WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=198812)します。</span><span class="sxs-lookup"><span data-stu-id="3149b-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3149b-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="3149b-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="3149b-108">WebBrowser コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3149b-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="3149b-109">WebBrowser コントロール</span><span class="sxs-lookup"><span data-stu-id="3149b-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)

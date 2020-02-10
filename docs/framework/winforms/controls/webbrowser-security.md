---
title: WebBrowser セキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095256"
---
# <a name="webbrowser-security"></a><span data-ttu-id="26e64-102">WebBrowser セキュリティ</span><span class="sxs-lookup"><span data-stu-id="26e64-102">WebBrowser Security</span></span>
<span data-ttu-id="26e64-103"><xref:System.Windows.Forms.WebBrowser> コントロールは、完全信頼のみで動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="26e64-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="26e64-104">コントロールに表示される HTML コンテンツは、外部 Web サーバーから取得でき、スクリプトまたは Web コントロールの形式でアンマネージコードを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="26e64-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="26e64-105">このような場合に <xref:System.Windows.Forms.WebBrowser> コントロールを使用すると、Internet Explorer の場合よりもコントロールの安全性は低くなりますが、マネージ <xref:System.Windows.Forms.WebBrowser> コントロールでは、このようなアンマネージコードの実行が妨げられることはありません。</span><span class="sxs-lookup"><span data-stu-id="26e64-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="26e64-106">基になる ActiveX `WebBrowser` コントロールに関連するセキュリティの問題の詳細については、「 [WebBrowser コントロール](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26e64-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e64-107">参照</span><span class="sxs-lookup"><span data-stu-id="26e64-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="26e64-108">WebBrowser コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="26e64-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="26e64-109">[WebBrowser コントロール](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="26e64-109">[WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>

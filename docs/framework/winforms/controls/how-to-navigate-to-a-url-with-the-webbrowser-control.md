---
title: '方法: WebBrowser コントロールで URL に移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: a174b6ae60f87e91e6f97e8fa7f8ad3892ef017a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913472"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="26e94-102">方法: WebBrowser コントロールで URL に移動する</span><span class="sxs-lookup"><span data-stu-id="26e94-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="26e94-103">次のコード例は、移動する方法を示します、<xref:System.Windows.Forms.WebBrowser>コントロールを特定の URL。</span><span class="sxs-lookup"><span data-stu-id="26e94-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="26e94-104">調べるには、新しいドキュメントが完全に読み込まれるときに、処理、<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>イベント。</span><span class="sxs-lookup"><span data-stu-id="26e94-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="26e94-105">このイベントのデモについては、次を参照してください。[方法。WebBrowser コントロールで印刷](how-to-print-with-a-webbrowser-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="26e94-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26e94-106">例</span><span class="sxs-lookup"><span data-stu-id="26e94-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="26e94-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="26e94-107">Compiling the Code</span></span>  
 <span data-ttu-id="26e94-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26e94-108">This example requires:</span></span>  
  
-   <span data-ttu-id="26e94-109">`webBrowser1` という名前の <xref:System.Windows.Forms.WebBrowser> コントロール。</span><span class="sxs-lookup"><span data-stu-id="26e94-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="26e94-110">`System` アセンブリおよび `System.Windows.Forms` アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="26e94-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e94-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="26e94-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="26e94-112">WebBrowser コントロール</span><span class="sxs-lookup"><span data-stu-id="26e94-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="26e94-113">方法: WebBrowser コントロールを使用して印刷します。</span><span class="sxs-lookup"><span data-stu-id="26e94-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)

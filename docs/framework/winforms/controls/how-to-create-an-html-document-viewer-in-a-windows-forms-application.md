---
title: '方法: Windows フォーム アプリケーションで HTML ドキュメントビューアーを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 99609e4bf5a352c436986e0773375d1c8e15e790
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746992"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="dc0ac-102">方法: Windows フォーム アプリケーションで HTML ドキュメントビューアーを作成する</span><span class="sxs-lookup"><span data-stu-id="dc0ac-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="dc0ac-103">使用することができます、<xref:System.Windows.Forms.WebBrowser>コントロールを表示し、インターネットの Web ブラウザーの完全な機能を提供することがなく HTML ドキュメントを印刷します。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="dc0ac-104">これは、機能は、HTML の書式設定機能を活用することが信頼されていない Web コントロールや悪意のあるスクリプト コードを含む可能性のある任意の Web ページの読み込みにユーザーを作成したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="dc0ac-105">機能を制限したい場合があります、 <xref:System.Windows.Forms.WebBrowser> HTML 電子メール ビューアーとして使用するか、アプリケーションで HTML 形式のヘルプを提供するなど、この方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="dc0ac-106">HTML ドキュメントビューアーを作成するには</span><span class="sxs-lookup"><span data-stu-id="dc0ac-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="dc0ac-107">設定、<xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>プロパティを`false`を防ぐために、<xref:System.Windows.Forms.WebBrowser>コントロールにドロップ ファイルを開けないようにします。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="dc0ac-108">設定、<xref:System.Windows.Forms.WebBrowser.Url%2A>プロパティを表示する最初のファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc0ac-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="dc0ac-109">Compiling the Code</span></span>  
 <span data-ttu-id="dc0ac-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-110">This example requires:</span></span>  
  
- <span data-ttu-id="dc0ac-111">`webBrowser1` という名前の <xref:System.Windows.Forms.WebBrowser> コントロール。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
- <span data-ttu-id="dc0ac-112">`System` アセンブリおよび `System.Windows.Forms` アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0ac-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc0ac-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="dc0ac-114">WebBrowser コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="dc0ac-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="dc0ac-115">WebBrowser セキュリティ</span><span class="sxs-lookup"><span data-stu-id="dc0ac-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="dc0ac-116">方法: WebBrowser コントロールで URL に移動します</span><span class="sxs-lookup"><span data-stu-id="dc0ac-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="dc0ac-117">方法: WebBrowser コントロールを使用して印刷します。</span><span class="sxs-lookup"><span data-stu-id="dc0ac-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)

---
title: '方法: マネージド HTML DOM (Document Object Model) にアクセスする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 2a195dc6583d5a0a72bd08b66f8933f4002e879a
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487275"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="6a36b-102">方法: マネージド HTML DOM (Document Object Model) にアクセスする</span><span class="sxs-lookup"><span data-stu-id="6a36b-102">How to: Access the Managed HTML Document Object Model</span></span>
<span data-ttu-id="6a36b-103">マネージド HTML ドキュメント オブジェクト モデル (DOM) には、次の 2 種類のアプリケーションからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6a36b-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
- <span data-ttu-id="6a36b-104">マネージド <xref:System.Windows.Forms.WebBrowser> コントロールをホストする Windows フォーム アプリケーション (.exe)。</span><span class="sxs-lookup"><span data-stu-id="6a36b-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="6a36b-105">この 2 つのテクノロジは相互に補完します。つまり、<xref:System.Windows.Forms.WebBrowser> コントロールはユーザーに対してページを表示し、HTML DOM はドキュメントの論理構造体を表します。</span><span class="sxs-lookup"><span data-stu-id="6a36b-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
- <span data-ttu-id="6a36b-106">Internet Explorer 内でホストされた Windows フォーム <xref:System.Windows.Forms.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="6a36b-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="6a36b-107"><xref:System.Windows.Forms.UserControl> をホストするページを表す HTML DOM にアクセスして、ドキュメントの構造体を変更したり、モーダル ダイアログ ボックスを開いたりするなど、さまざまな操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a36b-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="6a36b-108">Windows フォーム アプリケーションから DOM にアクセスするには</span><span class="sxs-lookup"><span data-stu-id="6a36b-108">To access DOM from a Windows Forms application</span></span>  
  
1. <span data-ttu-id="6a36b-109">Windows フォーム アプリケーション内で <xref:System.Windows.Forms.WebBrowser> コントロールをホストし、<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="6a36b-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="6a36b-110">コントロールのホストとイベントの監視の詳細については、「[イベント](../../../standard/events/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a36b-110">For details on hosting controls and monitoring for events, see [Events](../../../standard/events/index.md).</span></span>  
  
2. <span data-ttu-id="6a36b-111"><xref:System.Windows.Forms.HtmlDocument> コントロールの <xref:System.Windows.Forms.WebBrowser.Document%2A> プロパティにアクセスして、現在のページの <xref:System.Windows.Forms.WebBrowser> を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a36b-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="6a36b-112">Internet Explorer でホストされた UserControl から DOM にアクセスするには</span><span class="sxs-lookup"><span data-stu-id="6a36b-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1. <span data-ttu-id="6a36b-113"><xref:System.Windows.Forms.UserControl> クラスのカスタム派生クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a36b-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="6a36b-114">詳細については、「[方法 :複合コントロールを作成](how-to-author-composite-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="6a36b-114">For more information, see [How to: Author Composite Controls](how-to-author-composite-controls.md).</span></span>  
  
2. <span data-ttu-id="6a36b-115"><xref:System.Windows.Forms.UserControl> の Load イベント ハンドラー内に次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="6a36b-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6a36b-116">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="6a36b-116">Robust Programming</span></span>  
  
1. <span data-ttu-id="6a36b-117"><xref:System.Windows.Forms.WebBrowser> コントロールを通じて DOM を使用するときは、必ず <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> イベントが発生するまで待機してから <xref:System.Windows.Forms.WebBrowser.Document%2A> コントロールの <xref:System.Windows.Forms.WebBrowser> プロパティにアクセスするようにします。</span><span class="sxs-lookup"><span data-stu-id="6a36b-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="6a36b-118"><xref:System.Windows.Forms.WebBrowser.DocumentCompleted> イベントは、ドキュメント全体が読み込まれた後で発生します。それ以前に DOM を使用すると、アプリケーション内でランタイム例外が発生する恐れがあります。</span><span class="sxs-lookup"><span data-stu-id="6a36b-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6a36b-119">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6a36b-119">.NET Framework Security</span></span>  
  
1. <span data-ttu-id="6a36b-120">アプリケーションまたは <xref:System.Windows.Forms.UserControl> がマネージド HTML DOM にアクセスするには、完全信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a36b-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="6a36b-121">ClickOnce を使用して Windows フォーム アプリケーションを展開する場合は、アクセス許可の昇格または信頼されたアプリケーション配置; を使用して完全な信頼を要求することができます。参照してください[ClickOnce アプリケーションのセキュリティで保護する](/visualstudio/deployment/securing-clickonce-applications)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="6a36b-121">If you are deploying a Windows Forms application using ClickOnce, you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a36b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a36b-122">See also</span></span>

- [<span data-ttu-id="6a36b-123">マネージド HTML DOM (Document Object Model) の使用</span><span class="sxs-lookup"><span data-stu-id="6a36b-123">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)

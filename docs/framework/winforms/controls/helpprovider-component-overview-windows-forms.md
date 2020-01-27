---
title: HelpProvider コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738716"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="1cea6-102">HelpProvider コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="1cea6-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="1cea6-103">Windows フォーム[HelpProvider](helpprovider-component-windows-forms.md)コンポーネントは、Windows アプリケーションと共に html ヘルプ1.x ヘルプファイル (Html ヘルプワークショップで生成された .chm ファイル、または .htm ファイル) を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-103">The Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="1cea6-104">ヘルプは、次のさまざまな方法で提供できます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-104">You can provide help in a variety of ways:</span></span>  
  
- <span data-ttu-id="1cea6-105">Windows フォームのコントロールについて、状況依存のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="1cea6-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
- <span data-ttu-id="1cea6-106">ダイアログボックスの特定のダイアログボックスまたは特定のコントロールについて、状況依存のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="1cea6-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
- <span data-ttu-id="1cea6-107">目次のメインページ、インデックス、検索機能など、特定の領域に対してヘルプファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="1cea6-108">ヘルププロバイダーの使用</span><span class="sxs-lookup"><span data-stu-id="1cea6-108">Using the Help Provider</span></span>  
 <span data-ttu-id="1cea6-109">Windows フォームに <xref:System.Windows.Forms.HelpProvider> コンポーネントを追加すると、フォーム上の他のコントロールが <xref:System.Windows.Forms.HelpProvider> コンポーネントのヘルププロパティを公開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1cea6-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="1cea6-110">これにより、Windows フォーム上のコントロールにヘルプを提供できます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="1cea6-111"><xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> プロパティを使用して、ヘルプファイルを <xref:System.Windows.Forms.HelpProvider> コンポーネントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="1cea6-112">提供されるヘルプの種類を指定するには、<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> を呼び出し、指定したコントロールの <xref:System.Windows.Forms.HelpNavigator> 列挙体の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cea6-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="1cea6-113"><xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> メソッドを呼び出すことによって、ヘルプのキーワードまたはトピックを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cea6-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="1cea6-114">必要に応じて、特定のヘルプ文字列を別のコントロールに関連付けるには、<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1cea6-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="1cea6-115">コントロールにフォーカスがあるときにユーザーが F1 キーを押すと、このメソッドを使用してコントロールに関連付ける文字列がポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="1cea6-116"><xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> が設定されていない場合は、<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> を使用してヘルプテキストを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cea6-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="1cea6-117"><xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> とヘルプ文字列の両方を設定した場合は、<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> に基づくヘルプが優先されます。</span><span class="sxs-lookup"><span data-stu-id="1cea6-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cea6-118"><xref:System.Windows.Forms.HelpProvider> コントロールの <xref:System.Windows.Forms.Help.ShowHelp%2A> メソッドまたは <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> プロパティでヘルプファイルへのパスを指定するときに、相対パスを使用すると問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1cea6-118">You may encounter problems using the relative path when specifying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="1cea6-119">そのため、絶対ファイルパスを使用してヘルプファイルを指定してください。</span><span class="sxs-lookup"><span data-stu-id="1cea6-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cea6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cea6-120">See also</span></span>

- [<span data-ttu-id="1cea6-121">Windows フォーム アプリケーションのヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="1cea6-121">Help Systems in Windows Forms Applications</span></span>](../advanced/help-systems-in-windows-forms-applications.md)

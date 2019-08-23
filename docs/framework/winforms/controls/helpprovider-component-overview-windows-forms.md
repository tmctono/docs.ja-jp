---
title: HelpProvider コンポーネントの概要 (Windows フォーム)
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
ms.openlocfilehash: cefc590bb3011b282392504a78ac5c393c58493e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965695"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="d95ec-102">HelpProvider コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d95ec-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d95ec-103">Windows フォーム[HelpProvider](helpprovider-component-windows-forms.md)コンポーネントは、Windows アプリケーションと共に html ヘルプ1.x ヘルプファイル (Html ヘルプワークショップで生成された .chm ファイル、または .htm ファイル) を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d95ec-103">The Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="d95ec-104">ヘルプは、次のさまざまな方法で提供できます。</span><span class="sxs-lookup"><span data-stu-id="d95ec-104">You can provide help in a variety of ways:</span></span>  
  
- <span data-ttu-id="d95ec-105">Windows フォームのコントロールについて、状況依存のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="d95ec-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
- <span data-ttu-id="d95ec-106">ダイアログボックスの特定のダイアログボックスまたは特定のコントロールについて、状況依存のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="d95ec-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
- <span data-ttu-id="d95ec-107">目次のメインページ、インデックス、検索機能など、特定の領域に対してヘルプファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d95ec-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="d95ec-108">ヘルププロバイダーの使用</span><span class="sxs-lookup"><span data-stu-id="d95ec-108">Using the Help Provider</span></span>  
 <span data-ttu-id="d95ec-109">Windows フォーム<xref:System.Windows.Forms.HelpProvider>にコンポーネントを追加すると、フォーム上の他のコントロールが<xref:System.Windows.Forms.HelpProvider>コンポーネントのヘルププロパティを公開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d95ec-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="d95ec-110">これにより、Windows フォーム上のコントロールにヘルプを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d95ec-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="d95ec-111">プロパティを使用して、ヘルプファイル<xref:System.Windows.Forms.HelpProvider>をコンポーネントに関連付けることができます。 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="d95ec-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="d95ec-112">を呼び出し<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 、指定したコントロールの<xref:System.Windows.Forms.HelpNavigator>列挙体の値を指定して、提供されるヘルプの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d95ec-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="d95ec-113">ヘルプのキーワードまたはトピックは、 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>メソッドを呼び出すことによって指定します。</span><span class="sxs-lookup"><span data-stu-id="d95ec-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="d95ec-114">必要に応じて、特定のヘルプ文字列を別のコントロールに<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>関連付けるには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d95ec-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="d95ec-115">コントロールにフォーカスがあるときにユーザーが F1 キーを押すと、このメソッドを使用してコントロールに関連付ける文字列がポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d95ec-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="d95ec-116">が<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>設定されていない場合は<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 、を使用してヘルプテキストを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d95ec-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="d95ec-117">との両方<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>のヘルプ文字列を設定している場合は<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 、に基づくヘルプが優先されます。</span><span class="sxs-lookup"><span data-stu-id="d95ec-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d95ec-118">コントロールの<xref:System.Windows.Forms.Help.ShowHelp%2A>メソッドまたは<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>プロパティでヘルプファイルへのパスを指定するときに、相対パスを使用すると問題が発生することがあります。 <xref:System.Windows.Forms.HelpProvider></span><span class="sxs-lookup"><span data-stu-id="d95ec-118">You may encounter problems using the relative path when specifying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="d95ec-119">そのため、絶対ファイルパスを使用してヘルプファイルを指定してください。</span><span class="sxs-lookup"><span data-stu-id="d95ec-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d95ec-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d95ec-120">See also</span></span>

- [<span data-ttu-id="d95ec-121">Windows フォーム アプリケーションのヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="d95ec-121">Help Systems in Windows Forms Applications</span></span>](../advanced/help-systems-in-windows-forms-applications.md)

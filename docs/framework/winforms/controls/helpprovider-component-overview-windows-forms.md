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
ms.openlocfilehash: 9e8dc2ee2773b26a7bfef1da209399a8b49de9ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624125"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="befd2-102">HelpProvider コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="befd2-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="befd2-103">Windows フォーム[HelpProvider](helpprovider-component-windows-forms.md)に HTML ヘルプ 1.x のヘルプ ファイル (HTML Help Workshop で生成された .chm ファイル、または .htm ファイル) を Windows アプリケーションに関連付けるコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="befd2-103">The Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="befd2-104">さまざまな方法でヘルプを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="befd2-104">You can provide help in a variety of ways:</span></span>  
  
- <span data-ttu-id="befd2-105">Windows フォームのコントロールには、状況依存のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="befd2-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
- <span data-ttu-id="befd2-106">特定のダイアログ ボックスまたはダイアログ ボックスの特定のコントロールでは、状況依存のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="befd2-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
- <span data-ttu-id="befd2-107">テーブルの内容、インデックス、または検索関数のメイン ページなどの特定領域へのヘルプ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="befd2-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="befd2-108">ヘルプのプロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="befd2-108">Using the Help Provider</span></span>  
 <span data-ttu-id="befd2-109">追加、<xref:System.Windows.Forms.HelpProvider>を Windows フォームのコンポーネントは、のヘルプ プロパティを公開するフォーム上の他のコントロールを使用できます、<xref:System.Windows.Forms.HelpProvider>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="befd2-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="befd2-110">これにより、Windows フォーム上のコントロールのヘルプを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="befd2-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="befd2-111">ヘルプ ファイルを関連付けることができます、<xref:System.Windows.Forms.HelpProvider>コンポーネントを使用して、<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="befd2-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="befd2-112">呼び出すことによって提供されるヘルプの種類を指定する<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>から値を指定して、<xref:System.Windows.Forms.HelpNavigator>指定したコントロールの列挙体。</span><span class="sxs-lookup"><span data-stu-id="befd2-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="befd2-113">呼び出すことでヘルプのキーワードまたはトピックを提供する、<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="befd2-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="befd2-114">必要に応じて、特定のヘルプ文字列を別のコントロールに関連付けるに次のように使用します。、<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="befd2-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="befd2-115">このメソッドを使用するコントロールと関連付ける文字列は、コントロールにフォーカスがあるユーザーが F1 キーを押したときに、ポップアップ ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="befd2-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="befd2-116">場合<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>設定を使用する必要がありますが<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>ヘルプ テキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="befd2-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="befd2-117">両方を設定している場合<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>およびヘルプ文字列、ヘルプに基づいて<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>が優先されます。</span><span class="sxs-lookup"><span data-stu-id="befd2-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="befd2-118">ヘルプ ファイルへのパスを指定するときに、相対パスを使用して問題が発生する可能性があります、<xref:System.Windows.Forms.Help.ShowHelp%2A>メソッドまたは<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>のプロパティ、<xref:System.Windows.Forms.HelpProvider>コントロール。</span><span class="sxs-lookup"><span data-stu-id="befd2-118">You may encounter problems using the relative path when specifying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="befd2-119">したがって、ファイルの絶対パスを使用してヘルプ ファイルを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="befd2-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befd2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="befd2-120">See also</span></span>

- [<span data-ttu-id="befd2-121">Windows フォーム アプリケーションのヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="befd2-121">Help Systems in Windows Forms Applications</span></span>](../advanced/help-systems-in-windows-forms-applications.md)

---
title: '方法: Windows アプリケーションにヘルプを提供する'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 19bf6a8de3f9ddd5babd149747df87c54b456aeb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211364"
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="043f9-102">方法: Windows アプリケーションにヘルプを提供する</span><span class="sxs-lookup"><span data-stu-id="043f9-102">How to: Provide Help in a Windows Application</span></span>

<span data-ttu-id="043f9-103">使用することができます、<xref:System.Windows.Forms.HelpProvider>ヘルプ ファイル内のヘルプ トピックを特定の Windows フォーム コントロールにアタッチするコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="043f9-103">You can use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="043f9-104">ヘルプ ファイルの形式には、HTML または HTMLHelp 1.x 以上を指定できます。</span><span class="sxs-lookup"><span data-stu-id="043f9-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>

## <a name="provide-help"></a><span data-ttu-id="043f9-105">ヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="043f9-105">Provide Help</span></span>

1. <span data-ttu-id="043f9-106">Visual Studio から、**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.HelpProvider>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="043f9-106">In Visual Studio, from the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>

     <span data-ttu-id="043f9-107">コンポーネントは、Windows フォーム デザイナーの下部にあるトレイに配置されます。</span><span class="sxs-lookup"><span data-stu-id="043f9-107">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="043f9-108">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>プロパティを .chm、.col、または .htm ヘルプ ファイル。</span><span class="sxs-lookup"><span data-stu-id="043f9-108">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>

3. <span data-ttu-id="043f9-109">で、フォーム上にある別のコントロールを選択して、**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="043f9-109">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>

     <span data-ttu-id="043f9-110">これは、文字列が渡されます、<xref:System.Windows.Forms.HelpProvider>コンポーネント、ヘルプのファイルに適切なヘルプ トピックをします。</span><span class="sxs-lookup"><span data-stu-id="043f9-110">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>

4. <span data-ttu-id="043f9-111">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>プロパティの値を<xref:System.Windows.Forms.HelpNavigator>列挙体。</span><span class="sxs-lookup"><span data-stu-id="043f9-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>

     <span data-ttu-id="043f9-112">これにより、**HelpKeyword** プロパティがヘルプ システムに渡される方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="043f9-112">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="043f9-113">設定できるオプションとその説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="043f9-113">The following table shows the possible settings and their descriptions.</span></span>

    |<span data-ttu-id="043f9-114">メンバー名</span><span class="sxs-lookup"><span data-stu-id="043f9-114">Member Name</span></span>|<span data-ttu-id="043f9-115">説明</span><span class="sxs-lookup"><span data-stu-id="043f9-115">Description</span></span>|
    |-----------------|-----------------|
    |<span data-ttu-id="043f9-116">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="043f9-116">AssociateIndex</span></span>|<span data-ttu-id="043f9-117">指定したトピックのインデックスを指定した URL で実行するように指定します。</span><span class="sxs-lookup"><span data-stu-id="043f9-117">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|
    |<span data-ttu-id="043f9-118">[検索]</span><span class="sxs-lookup"><span data-stu-id="043f9-118">Find</span></span>|<span data-ttu-id="043f9-119">指定した URL の検索ページを表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="043f9-119">Specifies that the search page of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="043f9-120">インデックス</span><span class="sxs-lookup"><span data-stu-id="043f9-120">Index</span></span>|<span data-ttu-id="043f9-121">指定した URL のインデックスを表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="043f9-121">Specifies that the index of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="043f9-122">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="043f9-122">KeywordIndex</span></span>|<span data-ttu-id="043f9-123">検索するキーワードと、指定した URL で実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="043f9-123">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|
    |<span data-ttu-id="043f9-124">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="043f9-124">TableOfContents</span></span>|<span data-ttu-id="043f9-125">HTML 1.0 ヘルプ ファイルの目次を表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="043f9-125">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|
    |<span data-ttu-id="043f9-126">トピック</span><span class="sxs-lookup"><span data-stu-id="043f9-126">Topic</span></span>|<span data-ttu-id="043f9-127">指定した URL によって参照されるトピックを表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="043f9-127">Specifies that the topic referenced by the specified URL is displayed.</span></span>|

 <span data-ttu-id="043f9-128">F1 キーを押して、実行時とコントロール-設定が、 **HelpKeyword**と**HelpNavigator**プロパティ — がフォーカスと関連付けられたヘルプ ファイルを開きます<xref:System.Windows.Forms.HelpProvider>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="043f9-128">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>

 <span data-ttu-id="043f9-129">現時点では、 **HelpNamespace**プロパティは、次の 3 つの形式でのヘルプ ファイルをサポートしています。HTMLHelp 1.x、HTMLHelp 2.0、および HTML。</span><span class="sxs-lookup"><span data-stu-id="043f9-129">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="043f9-130">したがって、**HelpNamespace** プロパティには http:// アドレス (Web ページなど) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="043f9-130">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="043f9-131">プロパティに http:// アドレスを設定すると、既定のブラウザーが開き、**HelpKeyword** プロパティに指定した文字列をアンカーとして使用して Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="043f9-131">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="043f9-132">アンカーは HTML ページの特定の部分にジャンプするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="043f9-132">The anchor is used to jump to a specific part of an HTML page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="043f9-133">クライアントから送信された情報は、アプリケーションで使用する前に必ずチェックしてください。</span><span class="sxs-lookup"><span data-stu-id="043f9-133">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="043f9-134">悪意のあるユーザーが、実行可能スクリプトや SQL ステートメントなどのコードの送信 (挿入) を試みる場合があります。</span><span class="sxs-lookup"><span data-stu-id="043f9-134">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="043f9-135">ユーザーからの入力を表示したり、データベースに格納したり、操作したりする前に、安全でない可能性のある情報が含まれていないかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="043f9-135">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="043f9-136">一般的な確認方法としては、ユーザーから入力を受け取ったときに、正規表現を使用して、"SCRIPT" などのキーワードを検索します。</span><span class="sxs-lookup"><span data-stu-id="043f9-136">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>

<span data-ttu-id="043f9-137">使用することも、 <xref:System.Windows.Forms.HelpProvider> Windows フォーム上のコントロールのヘルプ ファイルを表示する構成している場合でも、ポップアップのヘルプを表示するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="043f9-137">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="043f9-138">詳細については、「[方法 :ポップアップ ヘルプを表示](how-to-display-pop-up-help.md)します。</span><span class="sxs-lookup"><span data-stu-id="043f9-138">For more information, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="043f9-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="043f9-139">See also</span></span>

- [<span data-ttu-id="043f9-140">方法: ポップアップ ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="043f9-140">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)
- [<span data-ttu-id="043f9-141">ツールヒントを使用したコントロールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="043f9-141">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="043f9-142">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="043f9-142">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="043f9-143">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="043f9-143">Windows Forms</span></span>](../index.md)

---
title: Windows フォーム アプリケーションのヘルプ システム
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 1a02271d59a59f0a6e06a652a34922ba5dcdf1f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937944"
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="2e22b-102">Windows フォーム アプリケーションのヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="2e22b-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="2e22b-103">1 つの最も重要な配慮をするように、アプリケーションの開発者は、ユーザーに提供できますが有能なヘルプ システムです。</span><span class="sxs-lookup"><span data-stu-id="2e22b-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="2e22b-104">これは、混乱または混乱になるときを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2e22b-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="2e22b-105">使用して簡単に行うは、Windows ベースのアプリケーションにヘルプ システムを提供する、 [HelpProvider コンポーネント](../controls/helpprovider-component-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e22b-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="2e22b-106">さまざまな種類のヘルプ</span><span class="sxs-lookup"><span data-stu-id="2e22b-106">Different Types of Help</span></span>  
 <span data-ttu-id="2e22b-107">Windows フォーム <xref:System.Windows.Forms.HelpProvider> コンポーネントは、Windows ベースのアプリケーションで HTML ヘルプ 1.x のヘルプ ファイル (HTML Help Workshop で生成された .chm ファイル、または .htm ファイル) を関連付けるために使用します。</span><span class="sxs-lookup"><span data-stu-id="2e22b-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="2e22b-108"><xref:System.Windows.Forms.HelpProvider>コンポーネントは、Windows フォーム上のコントロールまたはコントロールの特定の状況依存のヘルプを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e22b-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="2e22b-109">さらに、<xref:System.Windows.Forms.HelpProvider>コンポーネントは、コンテンツ、インデックス、または検索関数のテーブルのメイン ページなどの特定領域へのヘルプ ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2e22b-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="2e22b-110">概要については、<xref:System.Windows.Forms.HelpProvider>コンポーネントを参照してください[HelpProvider コンポーネントの概要](../controls/helpprovider-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e22b-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="2e22b-111">使用する方法については、 <xref:System.Windows.Forms.HelpProvider> 、Windows フォームのポップアップ ヘルプを表示するコンポーネントを参照してください[方法。ポップアップ ヘルプを表示](how-to-display-pop-up-help.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e22b-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="2e22b-112">使用方法について、<xref:System.Windows.Forms.ToolTip>コントロールに固有のヘルプを表示するコンポーネントを参照してください[コントロール ヘルプを使用してツールヒント](control-help-using-tooltips.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e22b-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="2e22b-113">HTML Help Workshop で HTML ヘルプ 1.x のファイルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="2e22b-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="2e22b-114">HTML ヘルプの詳細については、"HTML Help Workshop"または MSDN の他の"HTML"ヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e22b-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e22b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e22b-115">See also</span></span>

- [<span data-ttu-id="2e22b-116">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="2e22b-116">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="2e22b-117">HelpProvider コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2e22b-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)
- [<span data-ttu-id="2e22b-118">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2e22b-118">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)
- [<span data-ttu-id="2e22b-119">Windows フォームの概要</span><span class="sxs-lookup"><span data-stu-id="2e22b-119">Windows Forms Overview</span></span>](../windows-forms-overview.md)
- [<span data-ttu-id="2e22b-120">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="2e22b-120">Windows Forms</span></span>](../index.md)

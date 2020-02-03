---
title: ヘルプシステム
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: c97a22dbdbdcc0eb282b52e16c4ef40914b1d9e7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742249"
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="8dd6a-102">Windows フォーム アプリケーションのヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="8dd6a-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="8dd6a-103">アプリケーションの開発者として最も重要な courtesies の1つは、ユーザーがスキルの高いヘルプシステムを提供できることです。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="8dd6a-104">ここで、混乱または迷子が行われたときに、この場所が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="8dd6a-105">Windows ベースのアプリケーションでヘルプシステムを提供するには、 [HelpProvider コンポーネント](../controls/helpprovider-component-windows-forms.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="8dd6a-106">さまざまな種類のヘルプ</span><span class="sxs-lookup"><span data-stu-id="8dd6a-106">Different Types of Help</span></span>  
 <span data-ttu-id="8dd6a-107">Windows フォーム <xref:System.Windows.Forms.HelpProvider> コンポーネントは、Windows ベースのアプリケーションで HTML ヘルプ 1.x のヘルプ ファイル (HTML Help Workshop で生成された .chm ファイル、または .htm ファイル) を関連付けるために使用します。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="8dd6a-108"><xref:System.Windows.Forms.HelpProvider> コンポーネントは、Windows フォームまたは特定のコントロールのコントロールに対して、状況依存のヘルプを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="8dd6a-109">また、<xref:System.Windows.Forms.HelpProvider> コンポーネントでは、目次のメインページ、インデックス、検索機能など、特定の領域に対してヘルプファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="8dd6a-110"><xref:System.Windows.Forms.HelpProvider> コンポーネントに関する一般的な情報については、「 [HelpProvider コンポーネントの概要](../controls/helpprovider-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="8dd6a-111"><xref:System.Windows.Forms.HelpProvider> コンポーネントを使用して Windows フォームのポップアップヘルプを表示する方法については、「[方法: ポップアップヘルプを表示](how-to-display-pop-up-help.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="8dd6a-112"><xref:System.Windows.Forms.ToolTip> コンポーネントを使用してコントロール固有のヘルプを表示する方法の詳細については、「[ツールヒントを使用したコントロールのヘルプ](control-help-using-tooltips.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="8dd6a-113">Html ヘルプ 1. x ファイルは、HTML ヘルプワークショップを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="8dd6a-114">HTML ヘルプの詳細については、MSDN の「HTML ヘルプワークショップ」またはその他の「HTML ヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dd6a-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd6a-115">参照</span><span class="sxs-lookup"><span data-stu-id="8dd6a-115">See also</span></span>

- [<span data-ttu-id="8dd6a-116">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="8dd6a-116">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="8dd6a-117">HelpProvider コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8dd6a-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)
- [<span data-ttu-id="8dd6a-118">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8dd6a-118">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)
- [<span data-ttu-id="8dd6a-119">Windows フォームの概要</span><span class="sxs-lookup"><span data-stu-id="8dd6a-119">Windows Forms Overview</span></span>](../windows-forms-overview.md)
- [<span data-ttu-id="8dd6a-120">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="8dd6a-120">Windows Forms</span></span>](../index.md)

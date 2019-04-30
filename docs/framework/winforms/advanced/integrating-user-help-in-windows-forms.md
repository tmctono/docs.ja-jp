---
title: Windows フォームでのヘルプの統合
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942923"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="750cc-102">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="750cc-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="750cc-103">Windows ベースのアプリケーションの構築の非常に重要ですが、見落とされがちな側面はヘルプ システムをこれは、ユーザーが混乱したときにアシスタンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="750cc-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="750cc-104">Windows フォームでは、2 つの異なる種類のヘルプをサポート、それぞれによって提供される、 [HelpProvider コンポーネント](../controls/helpprovider-component-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="750cc-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="750cc-105">1 つ目は、HTML または HTML ヘルプ 1 のいずれかのヘルプ ファイルをユーザーを指す必要があります。*x*または大きい形式。</span><span class="sxs-lookup"><span data-stu-id="750cc-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="750cc-106">2 番目のことができますを表示する簡単な"と"-個々 のコントロールのヘルプを入力ダイアログ ボックスでは特に便利です。</span><span class="sxs-lookup"><span data-stu-id="750cc-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="750cc-107">両方の種類のヘルプは、同じフォームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="750cc-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="750cc-108">さらに、 [ToolTip コンポーネント](../controls/tooltip-component-windows-forms.md)Windows フォームのコントロールの個々 のヘルプを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="750cc-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="750cc-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="750cc-109">In This Section</span></span>  
 [<span data-ttu-id="750cc-110">方法: Windows アプリケーションにヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="750cc-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="750cc-111">使用する方法について説明します、`HelpProvider`ヘルプ システムのファイルにコントロールをリンクするコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="750cc-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="750cc-112">方法: ポップアップ ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="750cc-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="750cc-113">使用する方法について説明します、 `HelpProvider` Windows フォームのポップアップ ヘルプを表示するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="750cc-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="750cc-114">ツールヒントを使用したコントロールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="750cc-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="750cc-115">使用方法について説明、`ToolTip`コントロールに固有のヘルプを表示するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="750cc-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="750cc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="750cc-116">Related Sections</span></span>  
 [<span data-ttu-id="750cc-117">HelpProvider コンポーネント</span><span class="sxs-lookup"><span data-stu-id="750cc-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="750cc-118">基本について説明します、`HelpProvider`コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="750cc-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="750cc-119">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="750cc-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="750cc-120">基本について説明します、`ToolTip`コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="750cc-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="750cc-121">Windows フォームの概要</span><span class="sxs-lookup"><span data-stu-id="750cc-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="750cc-122">Windows フォームの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="750cc-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="750cc-123">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="750cc-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="750cc-124">Windows フォームの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="750cc-124">Provides an overview of Windows Forms.</span></span>

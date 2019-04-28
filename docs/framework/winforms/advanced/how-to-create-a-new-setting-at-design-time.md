---
title: '方法: 設計時に新しい設定を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: e371c60e3fb674e4243cec008e1098172725d4cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937723"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="f2617-102">方法: 設計時に新しい設定を作成する</span><span class="sxs-lookup"><span data-stu-id="f2617-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="f2617-103">設定デザイナーを使用して、デザイン時に新しい設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2617-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="f2617-104">設定デザイナーは、新しい設定を作成し、これらの設定のプロパティを指定できるようにするグリッド スタイルのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f2617-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="f2617-105">名前、値、型、および、新しい設定のスコープを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2617-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="f2617-106">設定が作成されると、コードでアクセス可能な。</span><span class="sxs-lookup"><span data-stu-id="f2617-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="f2617-107">C でのデザイン時に新しい設定を作成するには\#</span><span class="sxs-lookup"><span data-stu-id="f2617-107">To create a new setting at design time in C\#</span></span>
  
1. <span data-ttu-id="f2617-108">**ソリューション エクスプ ローラー**、展開、**プロパティ**プロジェクトのノード。</span><span class="sxs-lookup"><span data-stu-id="f2617-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2. <span data-ttu-id="f2617-109">新しい設定を追加する .settings ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2617-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="f2617-110">このファイルの既定の名前は Settings.settings ですです。</span><span class="sxs-lookup"><span data-stu-id="f2617-110">The default name for this file is Settings.settings.</span></span>  
  
3. <span data-ttu-id="f2617-111">設定デザイナーで、名前、値、型、および設定のスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="f2617-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="f2617-112">各行は、1 つの設定を表します。</span><span class="sxs-lookup"><span data-stu-id="f2617-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="f2617-113">Visual Basic でのデザイン時に新しい設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="f2617-113">To create a new setting at design time in Visual Basic</span></span>  
  
1. <span data-ttu-id="f2617-114">**ソリューション エクスプ ローラー**をプロジェクト ノードを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f2617-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="f2617-115">**プロパティ**] ページで、[、**設定**タブ。</span><span class="sxs-lookup"><span data-stu-id="f2617-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3. <span data-ttu-id="f2617-116">設定デザイナーで、名前、値、型、および設定のスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="f2617-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="f2617-117">各行は、1 つの設定を表します。</span><span class="sxs-lookup"><span data-stu-id="f2617-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2617-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2617-118">See also</span></span>

- [<span data-ttu-id="f2617-119">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="f2617-119">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="f2617-120">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="f2617-120">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="f2617-121">方法: デザイン時に既存の設定の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f2617-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)

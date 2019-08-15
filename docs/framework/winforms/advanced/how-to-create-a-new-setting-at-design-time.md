---
title: '方法: 設計時に新しい設定を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037902"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="35f4e-102">方法: デザイン時に新しい設定を作成する</span><span class="sxs-lookup"><span data-stu-id="35f4e-102">How To: Create a new setting at design time</span></span>

<span data-ttu-id="35f4e-103">Visual Studio の設定デザイナーを使用して、デザイン時に新しい設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="35f4e-103">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="35f4e-104">設定デザイナーは、新しい設定を作成し、それらの設定のプロパティを指定できるグリッド形式のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="35f4e-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="35f4e-105">新しい設定の名前、値、種類、およびスコープを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f4e-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="35f4e-106">設定が作成されると、コードでアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="35f4e-106">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="35f4e-107">C でデザイン時に新しい設定を作成する\#</span><span class="sxs-lookup"><span data-stu-id="35f4e-107">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="35f4e-108">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="35f4e-108">Open Visual Studio.</span></span>

2. <span data-ttu-id="35f4e-109">**ソリューションエクスプローラー**で、プロジェクトの **[プロパティ]** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-109">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="35f4e-110">新しい設定を追加する設定ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="35f4e-110">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="35f4e-111">このファイルの既定の名前は設定です。設定です。</span><span class="sxs-lookup"><span data-stu-id="35f4e-111">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="35f4e-112">設定デザイナーで、設定の **[名前]** 、 **[値]** 、 **[種類]** 、 **[スコープ]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-112">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="35f4e-113">各行は1つの設定を表します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-113">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="35f4e-114">デザイン時に Visual Basic で新しい設定を作成する</span><span class="sxs-lookup"><span data-stu-id="35f4e-114">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="35f4e-115">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="35f4e-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="35f4e-116">**ソリューションエクスプローラー**で、プロジェクトノードを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-116">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="35f4e-117">**[プロパティ]** ページで、 **[設定]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-117">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="35f4e-118">設定デザイナーで、設定の **[名前]** 、 **[値]** 、 **[種類]** 、 **[スコープ]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-118">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="35f4e-119">各行は1つの設定を表します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-119">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="35f4e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="35f4e-120">See also</span></span>

- [<span data-ttu-id="35f4e-121">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="35f4e-121">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="35f4e-122">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="35f4e-122">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="35f4e-123">方法: デザイン時に既存の設定の値を変更する</span><span class="sxs-lookup"><span data-stu-id="35f4e-123">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)

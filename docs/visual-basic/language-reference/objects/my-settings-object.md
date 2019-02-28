---
title: My.Settings オブジェクト (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 5d6d56e4a1eddcb687fe042568509ba489aa8bb3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973471"
---
# <a name="mysettings-object"></a><span data-ttu-id="2b7c0-102">My.Settings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2b7c0-102">My.Settings Object</span></span>
<span data-ttu-id="2b7c0-103">プロパティと、アプリケーションの設定にアクセスするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b7c0-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b7c0-104">Remarks</span></span>  
 <span data-ttu-id="2b7c0-105">`My.Settings`オブジェクトは、アプリケーションの設定へのアクセスを提供し、動的に格納し、プロパティの設定と、アプリケーションの他の情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="2b7c0-106">詳細については、「[アプリケーションの設定の管理 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2b7c0-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2b7c0-107">Properties</span></span>  
 <span data-ttu-id="2b7c0-108">`My.Settings` オブジェクトのプロパティを使用すると、アプリケーションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="2b7c0-109">を追加または削除の設定を使用して、**設定デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="2b7c0-110">各設定は、**名前**、**型**、**スコープ**と**値**、これらの設定を確認する方法各設定にアクセスするプロパティ表示されます、`My.Settings`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="2b7c0-111">**名前**プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="2b7c0-112">**型**プロパティの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="2b7c0-113">**スコープ**プロパティは読み取り専用のかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="2b7c0-114">値が場合**アプリケーション**、プロパティは読み取り専用です。 値の場合**ユーザー**、プロパティが読み取り/書き込みです。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="2b7c0-115">**値**はプロパティの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b7c0-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="2b7c0-116">Methods</span></span>  
  
|<span data-ttu-id="2b7c0-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="2b7c0-117">Method</span></span>|<span data-ttu-id="2b7c0-118">説明</span><span class="sxs-lookup"><span data-stu-id="2b7c0-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="2b7c0-119">最後に保存されている値からユーザーの設定を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="2b7c0-120">現在のユーザー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="2b7c0-121">`My.Settings`オブジェクトは、高度なプロパティとから継承されたメソッドにも提供します、<xref:System.Configuration.ApplicationSettingsBase>クラス。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="2b7c0-122">[タスク]</span><span class="sxs-lookup"><span data-stu-id="2b7c0-122">Tasks</span></span>  
 <span data-ttu-id="2b7c0-123">次の表に、関連するタスクの例については、`My.Settings`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="2b7c0-124">目的</span><span class="sxs-lookup"><span data-stu-id="2b7c0-124">To</span></span>|<span data-ttu-id="2b7c0-125">解決方法</span><span class="sxs-lookup"><span data-stu-id="2b7c0-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="2b7c0-126">アプリケーション設定を読み取り</span><span class="sxs-lookup"><span data-stu-id="2b7c0-126">Read an application setting</span></span>|[<span data-ttu-id="2b7c0-127">方法: Visual Basic でアプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="2b7c0-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="2b7c0-128">ユーザー設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-128">Change a user setting</span></span>|[<span data-ttu-id="2b7c0-129">方法: Visual Basic でユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="2b7c0-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="2b7c0-130">ユーザー設定します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-130">Persist user settings</span></span>|[<span data-ttu-id="2b7c0-131">方法: Visual Basic でユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="2b7c0-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="2b7c0-132">ユーザー設定のプロパティ グリッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="2b7c0-133">方法: Visual Basic でユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="2b7c0-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="2b7c0-134">例</span><span class="sxs-lookup"><span data-stu-id="2b7c0-134">Example</span></span>  
 <span data-ttu-id="2b7c0-135">次の例は、`Nickname` の設定値を表示します。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="2b7c0-136">この例を実行するには、アプリケーションで `String` 型の `Nickname` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b7c0-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7c0-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b7c0-137">See also</span></span>
- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="2b7c0-138">方法: Visual Basic でアプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="2b7c0-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="2b7c0-139">方法: Visual Basic でユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="2b7c0-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="2b7c0-140">方法: Visual Basic でユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="2b7c0-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="2b7c0-141">方法: Visual Basic でユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="2b7c0-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="2b7c0-142">アプリケーションの設定の管理 (.NET)</span><span class="sxs-lookup"><span data-stu-id="2b7c0-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

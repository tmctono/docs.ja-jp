---
title: My.Settings オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350361"
---
# <a name="mysettings-object"></a><span data-ttu-id="dcc33-102">My.Settings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dcc33-102">My.Settings Object</span></span>
<span data-ttu-id="dcc33-103">アプリケーションの設定にアクセスするためのプロパティとメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcc33-104">コメント</span><span class="sxs-lookup"><span data-stu-id="dcc33-104">Remarks</span></span>  
 <span data-ttu-id="dcc33-105">`My.Settings` オブジェクトは、アプリケーションの設定へのアクセスを提供し、アプリケーションのプロパティ設定やその他の情報を動的に格納および取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dcc33-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="dcc33-106">詳細については、[アプリケーションの設定の管理 (.NET)](/visualstudio/ide/managing-application-settings-dotnet) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcc33-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dcc33-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dcc33-107">Properties</span></span>  
 <span data-ttu-id="dcc33-108">`My.Settings` オブジェクトのプロパティを使用すると、アプリケーションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dcc33-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="dcc33-109">設定を追加または削除するには、**設定デザイナー**を使用します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="dcc33-110">各設定には**名前**、**種類**、**スコープ**、および**値**があり、これらの設定によって、各設定にアクセスするプロパティが `My.Settings` オブジェクトにどのように表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="dcc33-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="dcc33-111">**Name**プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="dcc33-112">**Type**は、プロパティの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="dcc33-113">**スコープ**は、プロパティが読み取り専用かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="dcc33-114">値が**アプリケーション**の場合、プロパティは読み取り専用です。値が**User**の場合、プロパティは読み取り/書き込み可能です。</span><span class="sxs-lookup"><span data-stu-id="dcc33-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="dcc33-115">**値**は、プロパティの既定値です。</span><span class="sxs-lookup"><span data-stu-id="dcc33-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcc33-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="dcc33-116">Methods</span></span>  
  
|<span data-ttu-id="dcc33-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="dcc33-117">Method</span></span>|<span data-ttu-id="dcc33-118">説明</span><span class="sxs-lookup"><span data-stu-id="dcc33-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="dcc33-119">最後に保存した値からユーザー設定を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="dcc33-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="dcc33-120">現在のユーザー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="dcc33-121">`My.Settings` オブジェクトは、<xref:System.Configuration.ApplicationSettingsBase> クラスから継承された高度なプロパティやメソッドも提供します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="dcc33-122">タスク</span><span class="sxs-lookup"><span data-stu-id="dcc33-122">Tasks</span></span>  
 <span data-ttu-id="dcc33-123">次の表に、`My.Settings` オブジェクトに関連するタスクの例を示します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="dcc33-124">目的</span><span class="sxs-lookup"><span data-stu-id="dcc33-124">To</span></span>|<span data-ttu-id="dcc33-125">参照先</span><span class="sxs-lookup"><span data-stu-id="dcc33-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="dcc33-126">アプリケーション設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="dcc33-126">Read an application setting</span></span>|[<span data-ttu-id="dcc33-127">方法: Visual Basic でアプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="dcc33-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="dcc33-128">ユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="dcc33-128">Change a user setting</span></span>|[<span data-ttu-id="dcc33-129">方法: Visual Basic でユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="dcc33-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="dcc33-130">ユーザー設定を保持する</span><span class="sxs-lookup"><span data-stu-id="dcc33-130">Persist user settings</span></span>|[<span data-ttu-id="dcc33-131">方法: Visual Basic でユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="dcc33-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="dcc33-132">ユーザー設定のプロパティグリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="dcc33-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="dcc33-133">方法: Visual Basic でユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="dcc33-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="dcc33-134">例</span><span class="sxs-lookup"><span data-stu-id="dcc33-134">Example</span></span>  
 <span data-ttu-id="dcc33-135">次の例は、`Nickname` の設定値を表示します。</span><span class="sxs-lookup"><span data-stu-id="dcc33-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="dcc33-136">この例を実行するには、アプリケーションで `Nickname` 型の `String` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcc33-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc33-137">参照</span><span class="sxs-lookup"><span data-stu-id="dcc33-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="dcc33-138">方法: Visual Basic でアプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="dcc33-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="dcc33-139">方法: Visual Basic でユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="dcc33-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="dcc33-140">方法: Visual Basic でユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="dcc33-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="dcc33-141">方法: Visual Basic でユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="dcc33-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="dcc33-142">アプリケーションの設定の管理 (.NET)</span><span class="sxs-lookup"><span data-stu-id="dcc33-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

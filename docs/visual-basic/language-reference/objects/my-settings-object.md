---
title: My.Settings オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867292"
---
# <a name="mysettings-object"></a><span data-ttu-id="75323-102">My.Settings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="75323-102">My.Settings Object</span></span>

<span data-ttu-id="75323-103">アプリケーションの設定にアクセスするためのプロパティとメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="75323-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75323-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="75323-104">Remarks</span></span>  

 <span data-ttu-id="75323-105">`My.Settings` オブジェクトは、アプリケーションの設定へのアクセスを提供し、アプリケーションのプロパティ設定やその他の情報を動的に格納し、取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="75323-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="75323-106">詳細については、「[アプリケーションの設定の管理 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75323-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="75323-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="75323-107">Properties</span></span>  

 <span data-ttu-id="75323-108">`My.Settings` オブジェクトのプロパティを使用すると、アプリケーションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="75323-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="75323-109">設定を追加または削除するには、**設定デザイナー**を使用します。</span><span class="sxs-lookup"><span data-stu-id="75323-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="75323-110">各設定には **[名前]** 、 **[型]** 、 **[スコープ]** 、および **[値]** が含まれ、これらの設定によって、各設定にアクセスするためのプロパティが `My.Settings` オブジェクトにどのように表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="75323-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="75323-111">**[名前]** は、プロパティの名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="75323-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="75323-112">**[型]** は、プロパティの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="75323-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="75323-113">**[スコープ]** は、プロパティが読み取り専用かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="75323-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="75323-114">値が **[アプリケーション]** の場合、プロパティは読み取り専用です。値が **[ユーザー]** の場合、プロパティは読み取り/書き込みです。</span><span class="sxs-lookup"><span data-stu-id="75323-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="75323-115">**[値]** はプロパティの既定値です。</span><span class="sxs-lookup"><span data-stu-id="75323-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75323-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="75323-116">Methods</span></span>  
  
|<span data-ttu-id="75323-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="75323-117">Method</span></span>|<span data-ttu-id="75323-118">説明</span><span class="sxs-lookup"><span data-stu-id="75323-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="75323-119">最後に保存した値からユーザー設定を再度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="75323-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="75323-120">現在のユーザー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="75323-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="75323-121">`My.Settings` オブジェクトは、<xref:System.Configuration.ApplicationSettingsBase> クラスから継承された高度なプロパティやメソッドも提供します。</span><span class="sxs-lookup"><span data-stu-id="75323-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="75323-122">タスク</span><span class="sxs-lookup"><span data-stu-id="75323-122">Tasks</span></span>  

 <span data-ttu-id="75323-123">次の表に、`My.Settings` オブジェクトに関連するタスクの例を示します。</span><span class="sxs-lookup"><span data-stu-id="75323-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="75323-124">終了</span><span class="sxs-lookup"><span data-stu-id="75323-124">To</span></span>|<span data-ttu-id="75323-125">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="75323-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="75323-126">アプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="75323-126">Read an application setting</span></span>|[<span data-ttu-id="75323-127">方法: Visual Basic でアプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="75323-127">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="75323-128">ユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="75323-128">Change a user setting</span></span>|[<span data-ttu-id="75323-129">方法: Visual Basic でユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="75323-129">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="75323-130">ユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="75323-130">Persist user settings</span></span>|[<span data-ttu-id="75323-131">方法: Visual Basic でユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="75323-131">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="75323-132">ユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="75323-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="75323-133">方法: Visual Basic でユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="75323-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="75323-134">例</span><span class="sxs-lookup"><span data-stu-id="75323-134">Example</span></span>  

 <span data-ttu-id="75323-135">次の例は、`Nickname` の設定値を表示します。</span><span class="sxs-lookup"><span data-stu-id="75323-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="75323-136">この例を実行するには、アプリケーションで `String` 型の `Nickname` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75323-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75323-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="75323-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="75323-138">方法: Visual Basic でアプリケーション設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="75323-138">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="75323-139">方法: Visual Basic でユーザー設定を変更する</span><span class="sxs-lookup"><span data-stu-id="75323-139">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="75323-140">方法: Visual Basic でユーザー設定を永続化する</span><span class="sxs-lookup"><span data-stu-id="75323-140">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="75323-141">方法: Visual Basic でユーザー設定のためのプロパティ グリッドを作成する</span><span class="sxs-lookup"><span data-stu-id="75323-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="75323-142">アプリケーションの設定の管理 (.NET)</span><span class="sxs-lookup"><span data-stu-id="75323-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

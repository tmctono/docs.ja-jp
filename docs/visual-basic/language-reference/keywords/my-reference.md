---
title: My の参照
ms.date: 07/20/2015
helpviewer_keywords:
- My feature
- My reference
ms.assetid: 6f803bd7-21ff-4569-b1fe-b00a6678b1e3
ms.openlocfilehash: 60dadc2918d4926c2b8bf1004a09d9b3a1ec56ab
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875574"
---
# <a name="my-reference-visual-basic"></a><span data-ttu-id="f865d-102">My の参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f865d-102">My Reference (Visual Basic)</span></span>

<span data-ttu-id="f865d-103">`My` 機能により、よく使用されるメソッド、プロパティ、およびイベントに直観的にアクセスできることで、プログラミングがより高速かつ簡単になります。</span><span class="sxs-lookup"><span data-stu-id="f865d-103">The `My` feature makes programming faster and easier by giving you intuitive access to commonly used methods, properties, and events.</span></span> <span data-ttu-id="f865d-104">次の表に、`My` に含まれるオブジェクトと、それぞれで実行できるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="f865d-104">This table lists the objects contained in `My`, and the actions that can be performed with each.</span></span>  
  
|<span data-ttu-id="f865d-105">**動作**</span><span class="sxs-lookup"><span data-stu-id="f865d-105">**Action**</span></span>|<span data-ttu-id="f865d-106">**オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="f865d-106">**Object**</span></span>|  
|----------------|----------------|  
|<span data-ttu-id="f865d-107">アプリケーション情報とサービスへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-107">Accessing application information and services.</span></span>|<span data-ttu-id="f865d-108">`My.Application` オブジェクトは、次のクラスで構成されています。</span><span class="sxs-lookup"><span data-stu-id="f865d-108">The `My.Application` object consists of the following classes:</span></span><br /><br /> <span data-ttu-id="f865d-109"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> は、すべてのプロジェクトで使用可能なメンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="f865d-109"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> provides members that are available in all projects.</span></span><br /><br /> <span data-ttu-id="f865d-110"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> は、Windows フォーム アプリケーションで使用可能なメンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="f865d-110"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> provides members available in Windows Forms applications.</span></span><br /><br /> <span data-ttu-id="f865d-111"><xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> は、コンソール アプリケーションで使用可能なメンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="f865d-111"><xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> provides members available in console applications.</span></span>|  
|<span data-ttu-id="f865d-112">ホスト コンピューターとそのリソース、サービス、およびデータへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-112">Accessing the host computer and its resources, services, and data.</span></span>|<span data-ttu-id="f865d-113">`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)</span><span class="sxs-lookup"><span data-stu-id="f865d-113">`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)</span></span>|  
|<span data-ttu-id="f865d-114">現在のプロジェクトのフォームへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-114">Accessing the forms in the current project.</span></span>|[<span data-ttu-id="f865d-115">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f865d-115">My.Forms Object</span></span>](../objects/my-forms-object.md)|  
|<span data-ttu-id="f865d-116">アプリケーション ログへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-116">Accessing the application log.</span></span>|<span data-ttu-id="f865d-117">`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)</span><span class="sxs-lookup"><span data-stu-id="f865d-117">`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)</span></span>|  
|<span data-ttu-id="f865d-118">現在の Web 要求へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-118">Accessing the current web request.</span></span>|[<span data-ttu-id="f865d-119">My.Request オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f865d-119">My.Request Object</span></span>](../objects/my-request-object.md)|  
|<span data-ttu-id="f865d-120">リソース要素へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-120">Accessing resource elements.</span></span>|[<span data-ttu-id="f865d-121">My.Resources オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f865d-121">My.Resources Object</span></span>](../objects/my-resources-object.md)|  
|<span data-ttu-id="f865d-122">現在の Web 応答へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-122">Accessing the current web response.</span></span>|[<span data-ttu-id="f865d-123">My.Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f865d-123">My.Response Object</span></span>](../objects/my-response-object.md)|  
|<span data-ttu-id="f865d-124">ユーザー レベルとアプリケーション レベルの設定へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-124">Accessing user and application level settings.</span></span>|[<span data-ttu-id="f865d-125">My.Settings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f865d-125">My.Settings Object</span></span>](../objects/my-settings-object.md)|  
|<span data-ttu-id="f865d-126">現在のユーザーのセキュリティ コンテキストへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-126">Accessing the current user's security context.</span></span>|<span data-ttu-id="f865d-127">`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)</span><span class="sxs-lookup"><span data-stu-id="f865d-127">`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)</span></span>|  
|<span data-ttu-id="f865d-128">現在のプロジェクトによって参照されている XML Web サービスへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f865d-128">Accessing XML Web services referenced by the current project.</span></span>|[<span data-ttu-id="f865d-129">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f865d-129">My.WebServices Object</span></span>](../objects/my-webservices-object.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f865d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f865d-130">See also</span></span>

- [<span data-ttu-id="f865d-131">Visual Basic アプリケーション モデルの概要</span><span class="sxs-lookup"><span data-stu-id="f865d-131">Overview of the Visual Basic Application Model</span></span>](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [<span data-ttu-id="f865d-132">My による開発</span><span class="sxs-lookup"><span data-stu-id="f865d-132">Development with My</span></span>](../../developing-apps/development-with-my/index.md)

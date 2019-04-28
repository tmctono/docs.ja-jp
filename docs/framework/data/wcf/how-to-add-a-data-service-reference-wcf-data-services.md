---
title: '方法: データ サービス参照 (WCF Data Services) の追加します。'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765532"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="1d27d-102">方法: データ サービス参照 (WCF Data Services) の追加します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="1d27d-103">使用することができます、**サービス参照の追加**WCF Data Services への参照を追加する Visual Studio でダイアログ。</span><span class="sxs-lookup"><span data-stu-id="1d27d-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="1d27d-104">参照をデータ サービスに追加すると、Visual Studio で開発したクライアント アプリケーションのデータ サービスに容易にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1d27d-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="1d27d-105">この手順を完了すると、データ サービスから取得されたメタデータに基づいてデータ クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1d27d-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="1d27d-106">詳細については、次を参照してください。[データ サービス クライアント ライブラリの生成](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="1d27d-107">データ サービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-107">Add a data service reference</span></span>

1. <span data-ttu-id="1d27d-108">(オプション) データ サービスがソリューションの一部ではなく、実行していない場合は、データ サービスを開始して、データ サービスの URI を記録します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="1d27d-109">Visual Studio での**ソリューション エクスプ ローラー**、クライアント プロジェクトを右クリックし、**追加** > **サービス参照の**します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="1d27d-110">データ サービスが現在のソリューションの一部である場合は、クリックして**Discover**します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="1d27d-111">- または -</span><span class="sxs-lookup"><span data-stu-id="1d27d-111">-or-</span></span>

     <span data-ttu-id="1d27d-112">**アドレス**テキスト ボックスに、入力、データ サービスのベース URL など`http://localhost:1234/Northwind.svc`、 をクリックし、**移動**します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="1d27d-113">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d27d-113">Select **OK**.</span></span>

     <span data-ttu-id="1d27d-114">アクセスして、データ サービス リソースとやり取りするデータ クラスを含む新しいコード ファイルは、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1d27d-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d27d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d27d-115">See also</span></span>

- [<span data-ttu-id="1d27d-116">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="1d27d-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
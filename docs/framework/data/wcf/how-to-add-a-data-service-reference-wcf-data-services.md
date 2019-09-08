---
title: '方法: データサービス参照の追加 (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 42d89cf87b5fe9bbdb229f10cd6a0e340d4c08fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790740"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="eb897-102">方法: データサービス参照の追加 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="eb897-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="eb897-103">Visual Studio の **[サービス参照の追加]** ダイアログボックスを使用して、WCF Data Services への参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="eb897-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="eb897-104">参照をデータ サービスに追加すると、Visual Studio で開発したクライアント アプリケーションのデータ サービスに容易にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eb897-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="eb897-105">この手順を完了すると、データ サービスから取得されたメタデータに基づいてデータ クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="eb897-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="eb897-106">詳細については、「[データサービスクライアントライブラリの生成](generating-the-data-service-client-library-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb897-106">For more information, see [Generating the Data Service Client Library](generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="eb897-107">データサービス参照の追加</span><span class="sxs-lookup"><span data-stu-id="eb897-107">Add a data service reference</span></span>

1. <span data-ttu-id="eb897-108">(オプション) データ サービスがソリューションの一部ではなく、実行していない場合は、データ サービスを開始して、データ サービスの URI を記録します。</span><span class="sxs-lookup"><span data-stu-id="eb897-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="eb897-109">Visual Studio の**ソリューションエクスプローラー**で、クライアントプロジェクトを右クリックし、[**サービス参照**の**追加** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb897-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="eb897-110">データサービスが現在のソリューションの一部である場合は、 **[探索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb897-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="eb897-111">\- または -</span><span class="sxs-lookup"><span data-stu-id="eb897-111">-or-</span></span>

     <span data-ttu-id="eb897-112">**[アドレス]** テキストボックスに、データサービスのベース URL (など) `http://localhost:1234/Northwind.svc`を入力し、[実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb897-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="eb897-113">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb897-113">Select **OK**.</span></span>

     <span data-ttu-id="eb897-114">データサービスリソースにアクセスして操作できるデータクラスを含む新しいコードファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="eb897-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb897-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb897-115">See also</span></span>

- [<span data-ttu-id="eb897-116">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="eb897-116">Quickstart</span></span>](quickstart-wcf-data-services.md)

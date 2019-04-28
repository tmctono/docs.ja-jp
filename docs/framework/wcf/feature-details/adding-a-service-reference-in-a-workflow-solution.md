---
title: ワークフロー ソリューションでのサービス参照の追加
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 8f1fa4604f1a1873c7063ec3c9dccf08bd0aa0ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669668"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a><span data-ttu-id="72964-102">ワークフロー ソリューションでのサービス参照の追加</span><span class="sxs-lookup"><span data-stu-id="72964-102">Adding a Service Reference in a Workflow Solution</span></span>

<span data-ttu-id="72964-103">ワークフロー アプリケーションでのサービス参照の追加は、通常の WCF アプリケーションとは動作が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="72964-103">Adding a service reference in a workflow application works a little differently than a regular WCF application.</span></span> <span data-ttu-id="72964-104">選択すると**追加 > サービス参照の**とサービスの URL を指定、メタデータをダウンロードおよびカスタム アクティビティが生成されることが WCF サービスまたはへの参照を追加した WCF ワークフロー サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="72964-104">When you select **Add > Service Reference** and specify the URL to the service, the metadata is downloaded and custom activities are generated that allow you to call the WCF service or WCF workflow service you added a reference to.</span></span> <span data-ttu-id="72964-105">サービス参照を追加した後、生成されたアクティビティがビルドされるように、ソリューションを再ビルドします。</span><span class="sxs-lookup"><span data-stu-id="72964-105">After adding a service reference, rebuild the solution so the generated activities are built.</span></span> <span data-ttu-id="72964-106">これにより、アクティビティがワークフロー デザイナー ツールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="72964-106">They will then appear in the workflow designer toolbox.</span></span> <span data-ttu-id="72964-107">ただし、この方法が機能するのはワークフロー ソリューション内でサービス参照を追加する場合だけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="72964-107">Note however, that this will only work if you are adding a service reference within a workflow solution.</span></span> <span data-ttu-id="72964-108">次の web キャストでは、その他の種類のプロジェクトでサービス参照を追加する方法を示します。[Web プロジェクトでのワークフローから WCF サービスを呼び出す](https://go.microsoft.com/fwlink/?LinkId=207725)します。</span><span class="sxs-lookup"><span data-stu-id="72964-108">The following web cast shows how to add a service reference in other types of projects: [Calling a WCF Service from a Workflow in a Web Project](https://go.microsoft.com/fwlink/?LinkId=207725).</span></span>

<span data-ttu-id="72964-109">同じ操作名が含まれるサービスへのサービス参照を複数追加すると、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="72964-109">Adding two or more service references to services that contain the same operation name will cause a problem.</span></span> <span data-ttu-id="72964-110">生成されたアクティビティは最初のサービス操作しか呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="72964-110">The generated activities will call only the first service operation.</span></span> <span data-ttu-id="72964-111">この問題を回避するには、サービス操作を別々の名前に変更するか、生成された各アクティビティ内でエンドポイント構成名を変更します。</span><span class="sxs-lookup"><span data-stu-id="72964-111">To work around this issue rename the service operations so they are different or change the endpoint configuration name within each generated activity.</span></span>

## <a name="see-also"></a><span data-ttu-id="72964-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="72964-112">See also</span></span>

- [<span data-ttu-id="72964-113">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="72964-113">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="72964-114">Web プロジェクトでのワークフローから WCF サービスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="72964-114">Calling a WCF Service from a Workflow in a Web Project</span></span>](https://go.microsoft.com/fwlink/?LinkId=207725)

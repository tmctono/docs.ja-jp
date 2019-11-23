---
title: コードとしてのインフラストラクチャ
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |コードとしてのインフラストラクチャ
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841781"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="6162c-103">コードとしてのインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="6162c-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6162c-104">クラウドネイティブアプリケーションでは、あらゆる種類の優れたサービスとしてのプラットフォーム (PaaS) コンポーネントを使用する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="6162c-104">Cloud-native applications tend to make use of all sorts of fantastic platform as a service (PaaS) components.</span></span> <span data-ttu-id="6162c-105">Azure のようなクラウドプラットフォームでは、これらのコンポーネントにストレージ、Service Bus、SignalR サービスなどが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6162c-105">On a cloud platform like Azure, these components might include things like storage, Service Bus, and the SignalR service.</span></span> <span data-ttu-id="6162c-106">アプリケーションが複雑になるにつれて、使用されているサービスの数が増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6162c-106">As applications become more complicated, the number of these services in use is likely to grow.</span></span> <span data-ttu-id="6162c-107">継続的デリバリーでは、環境への展開の従来のモデルが手動で中断されていたのと同じように、変更の迅速なペースにより、集中管理された IT グループが環境を管理するモデルも破損しています。</span><span class="sxs-lookup"><span data-stu-id="6162c-107">Just as how continuous delivery broke the traditional model of deploying to an environment manually, the rapid pace of change also broke the model of having a centralized IT group manage environments.</span></span>

<span data-ttu-id="6162c-108">環境の構築も自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="6162c-108">Building environments can, and should, also be automated.</span></span> <span data-ttu-id="6162c-109">プロセスを簡単にするための、非常に便利なツールが豊富に用意されています。</span><span class="sxs-lookup"><span data-stu-id="6162c-109">There's a wide range of well thought out tools that can make the process easy.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="6162c-110">Azure Resource Manager テンプレート</span><span class="sxs-lookup"><span data-stu-id="6162c-110">Azure Resource Manager templates</span></span>

<span data-ttu-id="6162c-111">Azure Resource Manager テンプレートは、Azure でさまざまなリソースを定義するための JSON ベースの言語です。</span><span class="sxs-lookup"><span data-stu-id="6162c-111">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="6162c-112">基本的なスキーマは、図11-10 のようになります。</span><span class="sxs-lookup"><span data-stu-id="6162c-112">The basic schema looks something like Figure 11-10.</span></span>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

<span data-ttu-id="6162c-113">**図 11-10** -Resource Manager テンプレートのスキーマ</span><span class="sxs-lookup"><span data-stu-id="6162c-113">**Figure 11-10** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="6162c-114">このテンプレート内では、次のように resources セクション内にストレージコンテナーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6162c-114">Within this template, one might define a storage container inside the resources section like so:</span></span>

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

<span data-ttu-id="6162c-115">**図 11-11** -Resource Manager テンプレートで定義されたストレージアカウントの例</span><span class="sxs-lookup"><span data-stu-id="6162c-115">**Figure 11-11** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="6162c-116">テンプレートをパラメーター化すると、1つのテンプレートをさまざまな設定で再利用して、開発、QA、および運用環境を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6162c-116">The templates can be parameterized so that one template can be reused with different settings to define development, QA, and production environments.</span></span> <span data-ttu-id="6162c-117">これにより、低い環境とは異なる方法で設定された、より高い環境に移行するときに予想外の事態を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="6162c-117">This helps eliminate surprises when migrating to a higher environment that is set up differently from the lower environments.</span></span> <span data-ttu-id="6162c-118">テンプレートで定義されたリソースは、通常、Azure 上の1つのリソースグループ内に作成されます (1 つの resource Manager テンプレートに複数のリソースグループを定義することはできますが、通常はそうではありません)。</span><span class="sxs-lookup"><span data-stu-id="6162c-118">The resources defined in a template are typically all created within a single resource group on Azure (it's possible to define multiple resource groups in a single Resource Manager template but unusual).</span></span> <span data-ttu-id="6162c-119">これにより、リソースグループ全体を削除するだけで、簡単に環境を削除できます。</span><span class="sxs-lookup"><span data-stu-id="6162c-119">This makes it very easy to delete an environment by just deleting the resource group as a whole.</span></span> <span data-ttu-id="6162c-120">コスト分析は、リソースグループレベルで実行することもできます。これにより、各環境のコストをすばやく計算できます。</span><span class="sxs-lookup"><span data-stu-id="6162c-120">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="6162c-121">GitHub の[Azure クイックスタートテンプレート](https://github.com/Azure/azure-quickstart-templates)プロジェクトで定義されているテンプレートの例の多くは、新しいテンプレートを開始するとき、または既存のテンプレートに追加するときに、脚を上げるために用意されています。</span><span class="sxs-lookup"><span data-stu-id="6162c-121">There are many example templates defined in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub that will give a leg up when starting on a new template or adding to an existing one.</span></span>

<span data-ttu-id="6162c-122">Resource Manager テンプレートは、さまざまな方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="6162c-122">Resource Manager templates can be run in a variety of ways.</span></span> <span data-ttu-id="6162c-123">おそらく、簡単な方法は、単に Azure portal に貼り付けることです。</span><span class="sxs-lookup"><span data-stu-id="6162c-123">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="6162c-124">試験的なデプロイの場合、この方法は非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="6162c-124">For experimental deployments, this method can be very quick.</span></span> <span data-ttu-id="6162c-125">また、Azure DevOps のビルドプロセスまたはリリースプロセスの一部として実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="6162c-125">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="6162c-126">Azure への接続を活用してテンプレートを実行するタスクがあります。</span><span class="sxs-lookup"><span data-stu-id="6162c-126">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="6162c-127">Resource Manager テンプレートへの変更は段階的に適用されます。つまり、新しいリソースを追加するには、テンプレートに追加するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="6162c-127">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="6162c-128">ツールは、テンプレートで定義されている目的のリソースグループを使用して、現在のリソースグループの比較を処理します。</span><span class="sxs-lookup"><span data-stu-id="6162c-128">The tooling will handle diffing the current resource group with the desired resource group defined in the template.</span></span> <span data-ttu-id="6162c-129">リソースは、テンプレートで定義されている内容と一致するように作成または変更されます。</span><span class="sxs-lookup"><span data-stu-id="6162c-129">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="6162c-130">Terraform</span><span class="sxs-lookup"><span data-stu-id="6162c-130">Terraform</span></span>

<span data-ttu-id="6162c-131">Resource Manager テンプレートの欠点は、Azure クラウドに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="6162c-131">A perceived disadvantage of Resource Manager templates is that they are specific to the Azure cloud.</span></span> <span data-ttu-id="6162c-132">複数のクラウドのリソースを含むアプリケーションを作成するのは普通ではありませんが、ビジネスが見事なアップタイムに依存している場合は、複数のクラウドをサポートするコストを意味することがあります。</span><span class="sxs-lookup"><span data-stu-id="6162c-132">It's unusual to create applications that include resources from more than one cloud, but in cases where the business relies on spectacular uptime, the cost of supporting multiple clouds might be worthwhile.</span></span> <span data-ttu-id="6162c-133">すべてのクラウドで使用できるテンプレート言語が1つある場合は、開発者のスキルをさらに移植しやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6162c-133">If there were one templating language that could be used across every cloud, then it would also allow for developer skills to be much more portable.</span></span>

<span data-ttu-id="6162c-134">いくつかのテクノロジが存在します。</span><span class="sxs-lookup"><span data-stu-id="6162c-134">Several technologies exist which do just that!</span></span> <span data-ttu-id="6162c-135">この領域で最も成熟したオファリングは[Terraform](https://www.terraform.io/)と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="6162c-135">The most mature offering in that space is known as [Terraform](https://www.terraform.io/).</span></span> <span data-ttu-id="6162c-136">Terraform は、Azure、Google Cloud Platform、AWS、AliCloud などのすべての主要クラウドプレーヤーをサポートします。また、Heroku や DigitalOcean など、多数の小規模なプレーヤーもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6162c-136">Terraform supports every major cloud player such as Azure, Google Cloud Platform, AWS, and AliCloud, and it also supports dozens of minor players such as Heroku and DigitalOcean.</span></span> <span data-ttu-id="6162c-137">JSON をテンプレート定義言語として使用する代わりに、やや簡潔な YAML を使用します。</span><span class="sxs-lookup"><span data-stu-id="6162c-137">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="6162c-138">前の Resource Manager テンプレートと同様の Terraform ファイルの例 (図 11-11) を図11-12 に示します。</span><span class="sxs-lookup"><span data-stu-id="6162c-138">An example Terraform file that does the same as the previous Resource Manager template (Figure 11-11) is shown in Figure 11-12:</span></span>

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

<span data-ttu-id="6162c-139">**図 11-12** -Resource Manager テンプレートの例</span><span class="sxs-lookup"><span data-stu-id="6162c-139">**Figure 11-12** - An example of a Resource Manager template</span></span>

<span data-ttu-id="6162c-140">Terraform では、テンプレートでエラーが発生したためにリソースをデプロイできない場合に、適切なエラーメッセージを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="6162c-140">Terraform does a better job of providing sensible error messages when a resource can't be deployed because of an error in the template.</span></span> <span data-ttu-id="6162c-141">これは、Resource Manager テンプレートが進行中の課題を抱えている領域です。</span><span class="sxs-lookup"><span data-stu-id="6162c-141">This is an area where Resource Manager templates have some ongoing challenges.</span></span> <span data-ttu-id="6162c-142">また、テンプレートエラーを早期にキャッチするためにビルドフェーズで使用できる、非常に便利な検証タスクもあります。</span><span class="sxs-lookup"><span data-stu-id="6162c-142">There's also a very handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="6162c-143">Resource Manager テンプレートと同様に、Terraform テンプレートのデプロイに使用できるコマンドラインツールがあります。</span><span class="sxs-lookup"><span data-stu-id="6162c-143">As with Resource Manager templates, there are command-line tools that can be used to deploy Terraform templates.</span></span> <span data-ttu-id="6162c-144">また、Azure Pipelines には、Terraform テンプレートを検証して適用できるコミュニティによって作成されたタスクもあります。</span><span class="sxs-lookup"><span data-stu-id="6162c-144">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="6162c-145">Terraform テンプレートまたは Resource Manager テンプレートが、新しく作成されたデータベースへの接続文字列などの興味深い値を出力する場合、ビルドパイプラインでキャプチャし、後続のタスクで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6162c-145">In the event that the Terraform or Resource Manager template outputs interesting values such as the connection string to a newly created database they can be captured in the build pipeline and used in subsequent tasks.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6162c-146">[前へ](devops.md)
>[次へ](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="6162c-146">[Previous](devops.md)
[Next](application-bundles.md)</span></span>

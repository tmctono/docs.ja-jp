---
title: モデル アイテム ツリーのプログラミング
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f14b140fdac95f3763cc5625841a725793876fa4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142694"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="113ac-102">モデル アイテム ツリーのプログラミング</span><span class="sxs-lookup"><span data-stu-id="113ac-102">Programming Model Item Tree</span></span>
<span data-ttu-id="113ac-103">このサンプルでは、Windows プレゼンテーションファン<xref:System.Activities.Presentation.Model.ModelItem>デーション (WPF) ツリー ビューから宣言型データ バインディングを使用してツリーを移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="113ac-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="113ac-104">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="113ac-104">Sample Details</span></span>
 <span data-ttu-id="113ac-105">ツリー<xref:System.Activities.Presentation.Model.ModelItem>は、Windows ワークフロー デザイナー インフラストラクチャで使用される抽象化で、編集対象の基になるインスタンスに関するデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="113ac-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="113ac-106">次の図は、ワークフロー デザイナー内のさまざまなインフラストラクチャ 層を示しています。</span><span class="sxs-lookup"><span data-stu-id="113ac-106">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![ワークフロー デザイナーのアーキテクチャを示す図。](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="113ac-108"><xref:System.Activities.Presentation.Model.ModelItem> は、基になる値へのポインターと、<xref:System.Activities.Presentation.Model.ModelProperty> オブジェクトのコレクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="113ac-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="113ac-109"><xref:System.Activities.Presentation.Model.ModelProperty> オブジェクトはさらに、プロパティの名前や型などのデータと、また別の <xref:System.Activities.Presentation.Model.ModelItem> である値へのポインターで構成されています。</span><span class="sxs-lookup"><span data-stu-id="113ac-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="113ac-110"><xref:System.Activities.Presentation.Model.ModelItem> から返される一部の <xref:System.Activities.Presentation.Model.ModelProperty> に対しては、ツリー ビューに正しく表示されるように操作するために値コンバーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="113ac-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="113ac-111">このサンプルでは、次の例のような命令構文を使用して <xref:System.Activities.Presentation.Model.ModelItem> ツリーを命令型プログラミングで操作する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="113ac-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="113ac-112">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="113ac-112">To use this sample</span></span>

1. <span data-ttu-id="113ac-113">2010 年にプログラムモデルアイテムツリー.sln ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="113ac-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="113ac-114">[ビルド] メニューの [**ソリューションのビルド**] を選択してソリューションを**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="113ac-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="113ac-115">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="113ac-115">Press F5 to run the application.</span></span> <span data-ttu-id="113ac-116">その後、WPF フォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="113ac-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="113ac-117">[WF**のロード**] ボタン<xref:System.Activities.Presentation.Model.ModelItem>をクリックして、 をロードし、ツリー ビューにバインドします。</span><span class="sxs-lookup"><span data-stu-id="113ac-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="113ac-118">[**モデル アイテム ツリーの変更]** ボタンをクリックすると、上記のコードが実行され、ツリーに項目が追加され、プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="113ac-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="113ac-119">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="113ac-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="113ac-120">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="113ac-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="113ac-121">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="113ac-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="113ac-122">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="113ac-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="113ac-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="113ac-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>

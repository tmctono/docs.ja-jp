---
title: カスタム複合デザイナー - Workflow Item Presenter
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: 31dfae70a8b95bdfd457efe7a20ce44c2ba9c61f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715185"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="ab146-102">カスタム複合デザイナー - Workflow Item Presenter</span><span class="sxs-lookup"><span data-stu-id="ab146-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="ab146-103"><xref:System.Activities.Presentation.WorkflowItemPresenter> は、任意のアクティビティを配置できる "ドロップゾーン" の作成を可能にする WF デザイナープログラミングモデルのキーの種類です。</span><span class="sxs-lookup"><span data-stu-id="ab146-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="ab146-104">このサンプルでは、このような "ドロップゾーン" を格納するアクティビティデザイナーを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab146-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

 <span data-ttu-id="ab146-105">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab146-105">This sample demonstrates:</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ab146-106">例</span><span class="sxs-lookup"><span data-stu-id="ab146-106">Demonstrates</span></span>

- <span data-ttu-id="ab146-107"><xref:System.Activities.Presentation.WorkflowItemPresenter> を使用したカスタム アクティビティ デザイナーの作成</span><span class="sxs-lookup"><span data-stu-id="ab146-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="ab146-108">メタデータ ストアを使用したカスタム デザイナーの登録。</span><span class="sxs-lookup"><span data-stu-id="ab146-108">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="ab146-109">宣言および命令による再ホストされたツールボックスのプログラミング。</span><span class="sxs-lookup"><span data-stu-id="ab146-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="ab146-110">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="ab146-110">Sample Details</span></span>
 <span data-ttu-id="ab146-111">このサンプルのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ab146-111">The code for this sample shows:</span></span>

- <span data-ttu-id="ab146-112">カスタム アクティビティ デザイナーは `SimpleNativeActivity` クラス用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="ab146-113"><xref:System.Activities.Presentation.WorkflowItemPresenter> を使用してカスタム アクティビティ デザイナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab146-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

```xaml
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
    <sap:ActivityDesigner.Resources>
        <DataTemplate x:Key="Collapsed">
            <StackPanel>
                <TextBlock>This is the collapsed view</TextBlock>
            </StackPanel>
        </DataTemplate>
        <DataTemplate x:Key="Expanded">
            <StackPanel>
                <TextBlock>Custom Text</TextBlock>
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                        HintText="Please drop an activity here" />
            </StackPanel>
        </DataTemplate>
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
            <Style.Triggers>
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                </DataTrigger>
            </Style.Triggers>
        </Style>
    </sap:ActivityDesigner.Resources>
    <Grid>
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
    </Grid>
</sap:ActivityDesigner>
```

 <span data-ttu-id="ab146-114">`ModelItem.Body` にバインドする WPF のデータ バインディングの使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="ab146-115">`ModelItem` は、デザイナーが使用されている基になるオブジェクト (この場合は**simplenativeactivity)** ) を参照する <xref:System.Activities.Presentation.ActivityDesigner> のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ab146-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="ab146-116">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="ab146-116">To setup, build, and run the sample</span></span>

1. <span data-ttu-id="ab146-117">Visual Studio 2010 でソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="ab146-117">Open the solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="ab146-118">F5 キーを押してアプリケーションをコンパイルし、実行します。</span><span class="sxs-lookup"><span data-stu-id="ab146-118">Press F5 to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab146-119">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab146-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ab146-120">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="ab146-121">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459)にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) と [!INCLUDE[wf1](../../../../includes/wf1-md.md)] サンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="ab146-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab146-122">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="ab146-123">参照</span><span class="sxs-lookup"><span data-stu-id="ab146-123">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="ab146-124">ワークフロー デザイナーを使用したアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="ab146-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)

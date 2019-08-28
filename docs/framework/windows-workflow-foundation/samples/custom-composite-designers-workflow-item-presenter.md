---
title: カスタム複合デザイナー - Workflow Item Presenter
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: 239f7ccd81d5bb60eed32298220df215b09e3e47
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038370"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="415d4-102">カスタム複合デザイナー - Workflow Item Presenter</span><span class="sxs-lookup"><span data-stu-id="415d4-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="415d4-103"><xref:System.Activities.Presentation.WorkflowItemPresenter>は、任意のアクティビティを配置できる "ドロップゾーン" の作成を可能にする WF デザイナープログラミングモデルのキーの種類です。</span><span class="sxs-lookup"><span data-stu-id="415d4-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="415d4-104">このサンプルでは、このような "ドロップゾーン" を格納するアクティビティデザイナーを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="415d4-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

 <span data-ttu-id="415d4-105">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="415d4-105">This sample demonstrates:</span></span>

## <a name="demonstrates"></a><span data-ttu-id="415d4-106">使用例</span><span class="sxs-lookup"><span data-stu-id="415d4-106">Demonstrates</span></span>

- <span data-ttu-id="415d4-107"><xref:System.Activities.Presentation.WorkflowItemPresenter> を使用したカスタム アクティビティ デザイナーの作成</span><span class="sxs-lookup"><span data-stu-id="415d4-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="415d4-108">メタデータ ストアを使用したカスタム デザイナーの登録。</span><span class="sxs-lookup"><span data-stu-id="415d4-108">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="415d4-109">宣言および命令による再ホストされたツールボックスのプログラミング。</span><span class="sxs-lookup"><span data-stu-id="415d4-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="415d4-110">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="415d4-110">Sample Details</span></span>
 <span data-ttu-id="415d4-111">このサンプルのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="415d4-111">The code for this sample shows:</span></span>

- <span data-ttu-id="415d4-112">カスタム アクティビティ デザイナーは `SimpleNativeActivity` クラス用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="415d4-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="415d4-113"><xref:System.Activities.Presentation.WorkflowItemPresenter> を使用してカスタム アクティビティ デザイナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="415d4-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

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

 <span data-ttu-id="415d4-114">`ModelItem.Body` にバインドする WPF のデータ バインドの使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="415d4-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="415d4-115">`ModelItem`は、デザイナーが<xref:System.Activities.Presentation.ActivityDesigner>使用されている基になるオブジェクト (この場合は**simplenativeactivity)** ) を参照するのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="415d4-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="415d4-116">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="415d4-116">To setup, build, and run the sample</span></span>

1. <span data-ttu-id="415d4-117">Visual Studio 2010 でソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="415d4-117">Open the solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="415d4-118">F5 キーを押してアプリケーションをコンパイルし、実行します。</span><span class="sxs-lookup"><span data-stu-id="415d4-118">Press F5 to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="415d4-119">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="415d4-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="415d4-120">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="415d4-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="415d4-121">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="415d4-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="415d4-122">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="415d4-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="415d4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="415d4-123">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="415d4-124">ワークフロー デザイナーを使用したアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="415d4-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)

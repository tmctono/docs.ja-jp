---
title: TryCatch を使用した Flowchart アクティビティでのエラー処理
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 3f45d4a60de3201a3100fba3af6cc15484a1fbf0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708835"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="ee86d-102">TryCatch を使用した Flowchart アクティビティでのエラー処理</span><span class="sxs-lookup"><span data-stu-id="ee86d-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>
<span data-ttu-id="ee86d-103">このサンプルでは、複雑な制御フロー アクティビティ内で <xref:System.Activities.Statements.TryCatch> アクティビティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee86d-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>

 <span data-ttu-id="ee86d-104">このサンプルでは、販売促進コードに対応する式に基づいて割引率を計算する <xref:System.Activities.Statements.Flowchart> アクティビティに、販売促進コードと子供の数が変数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="ee86d-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="ee86d-105">このサンプルには、命令型コードとワークフロー デザイナー バージョンのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee86d-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>

 <span data-ttu-id="ee86d-106">次の表で、`CreateFlowchartWithFaults` アクティビティの変数の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="ee86d-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>

|<span data-ttu-id="ee86d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee86d-107">Parameters</span></span>|<span data-ttu-id="ee86d-108">説明</span><span class="sxs-lookup"><span data-stu-id="ee86d-108">Description</span></span>|
|----------------|-----------------|
|<span data-ttu-id="ee86d-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="ee86d-109">promoCode</span></span>|<span data-ttu-id="ee86d-110">販売促進コード。</span><span class="sxs-lookup"><span data-stu-id="ee86d-110">The promotion code.</span></span> <span data-ttu-id="ee86d-111">型:String</span><span class="sxs-lookup"><span data-stu-id="ee86d-111">Type: String</span></span><br /><br /> <span data-ttu-id="ee86d-112">使用できる値は次のとおりです (かっこ内は値の説明)。</span><span class="sxs-lookup"><span data-stu-id="ee86d-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="ee86d-113">-単一 (単一)</span><span class="sxs-lookup"><span data-stu-id="ee86d-113">-   Single (Single)</span></span><br /><span data-ttu-id="ee86d-114">MNK (子供の既婚。)</span><span class="sxs-lookup"><span data-stu-id="ee86d-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="ee86d-115">MWK (子供の既婚。)</span><span class="sxs-lookup"><span data-stu-id="ee86d-115">-   MWK (Married with kids.)</span></span>|
|<span data-ttu-id="ee86d-116">numKids</span><span class="sxs-lookup"><span data-stu-id="ee86d-116">numKids</span></span>|<span data-ttu-id="ee86d-117">子供の数。</span><span class="sxs-lookup"><span data-stu-id="ee86d-117">The number of children.</span></span> <span data-ttu-id="ee86d-118">型: int</span><span class="sxs-lookup"><span data-stu-id="ee86d-118">Type: int</span></span>|

 <span data-ttu-id="ee86d-119">`CreateFlowchartWithFaults` アクティビティでは、<xref:System.Activities.Statements.FlowSwitch%601> 引数を有効にする `promoCode` アクティビティを使用し、次の式を使って割引率を計算します。</span><span class="sxs-lookup"><span data-stu-id="ee86d-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>

|<span data-ttu-id="ee86d-120">`promoCode` の値</span><span class="sxs-lookup"><span data-stu-id="ee86d-120">Value of `promoCode`</span></span>|<span data-ttu-id="ee86d-121">割引率 (%)</span><span class="sxs-lookup"><span data-stu-id="ee86d-121">Discount (%)</span></span>|
|--------------------------|--------------------|
|<span data-ttu-id="ee86d-122">Single</span><span class="sxs-lookup"><span data-stu-id="ee86d-122">Single</span></span>|<span data-ttu-id="ee86d-123">10</span><span class="sxs-lookup"><span data-stu-id="ee86d-123">10</span></span>|
|<span data-ttu-id="ee86d-124">MNK</span><span class="sxs-lookup"><span data-stu-id="ee86d-124">MNK</span></span>|<span data-ttu-id="ee86d-125">16</span><span class="sxs-lookup"><span data-stu-id="ee86d-125">15</span></span>|
|<span data-ttu-id="ee86d-126">MWK</span><span class="sxs-lookup"><span data-stu-id="ee86d-126">MWK</span></span>|<span data-ttu-id="ee86d-127">15 + (1 – 1/`numberOfKids`)\*10**に注意してください。** この計算では、<xref:System.DivideByZeroException> がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee86d-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="ee86d-128">そのため、割引率の計算は、<xref:System.Activities.Statements.TryCatch> 例外をキャッチして割引率をゼロに設定する <xref:System.DivideByZeroException> アクティビティでラップされます。</span><span class="sxs-lookup"><span data-stu-id="ee86d-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="ee86d-129">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="ee86d-129">To use this sample</span></span>

1.  <span data-ttu-id="ee86d-130">Visual Studio 2010 を使用して、FlowchartWithFaultHandling.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee86d-130">Using Visual Studio 2010, open the FlowchartWithFaultHandling.sln solution file.</span></span>

2.  <span data-ttu-id="ee86d-131">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ee86d-131">To build the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="ee86d-132">ソリューションを実行するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ee86d-132">To run the solution, press F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="ee86d-133">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ee86d-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ee86d-134">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ee86d-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ee86d-135">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="ee86d-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee86d-136">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ee86d-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a><span data-ttu-id="ee86d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee86d-137">See also</span></span>
- [<span data-ttu-id="ee86d-138">Flowchart のワークフロー</span><span class="sxs-lookup"><span data-stu-id="ee86d-138">Flowchart Workflows</span></span>](../flowchart-workflows.md)
- [<span data-ttu-id="ee86d-139">例外</span><span class="sxs-lookup"><span data-stu-id="ee86d-139">Exceptions</span></span>](../exceptions.md)

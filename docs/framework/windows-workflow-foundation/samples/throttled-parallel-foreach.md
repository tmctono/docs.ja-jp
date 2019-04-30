---
title: 制限された並列 ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: fd30a1ac587359a054a273b3deca2e9bb8bc2798
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004862"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="75096-102">制限された並列 ForEach</span><span class="sxs-lookup"><span data-stu-id="75096-102">Throttled Parallel ForEach</span></span>

<span data-ttu-id="75096-103">`ThrottleParallelForEach` アクティビティは、実行する同時分岐の数を制限するためのコンカレンシー要因を設定できるという 1 つの例外を除き、<xref:System.Activities.Statements.ParallelForEach%601> アクティビティと似ていることについて示します。</span><span class="sxs-lookup"><span data-stu-id="75096-103">The `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="75096-104">`ThrottleParallelForEach` アクティビティは、<xref:System.Activities.NativeActivity> クラスを介してのみアクセスできる他のアクティビティ (子アクティビティ) をスケジュールする必要があるため、<xref:System.Activities.NativeActivityContext> クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="75096-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="75096-105">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="75096-105">Projects</span></span>

|<span data-ttu-id="75096-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="75096-106">**ProjectName**</span></span>|<span data-ttu-id="75096-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="75096-107">**Description**</span></span>|<span data-ttu-id="75096-108">**メイン ファイル**</span><span class="sxs-lookup"><span data-stu-id="75096-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="75096-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="75096-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="75096-110">`ThrottledParallelForEach` アクティビティとそのデザイナーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="75096-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="75096-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="75096-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="75096-112">`ThrottledParallelForEach` アクティビティ定義。</span><span class="sxs-lookup"><span data-stu-id="75096-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="75096-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="75096-113">CodeTestClient</span></span>|<span data-ttu-id="75096-114">命令型コードを使用して、`ThrottledParallelForEach` を含むワークフローを構成および実行するサンプル クライアント アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="75096-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="75096-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="75096-115">Program.cs</span></span><br /><br /> <span data-ttu-id="75096-116">サンプル ワークフローのインスタンスを定義および実行します。</span><span class="sxs-lookup"><span data-stu-id="75096-116">Defines and runs an instance of the sample workflow.</span></span>|

## <a name="to-use-this-sample"></a><span data-ttu-id="75096-117">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="75096-117">To use this sample</span></span>

1. <span data-ttu-id="75096-118">Visual Studio 2010 を使用して、ThrottledParallelForEach.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="75096-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2. <span data-ttu-id="75096-119">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="75096-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="75096-120">ソリューションを実行するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="75096-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75096-121">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="75096-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="75096-122">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="75096-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="75096-123">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="75096-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="75096-124">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="75096-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`
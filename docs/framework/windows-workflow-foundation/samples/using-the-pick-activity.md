---
title: Pick アクティビティの使用
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 0b2fbeb9b32406dd913d7e1ee87ac167113d0f28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004732"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="3dcef-102">Pick アクティビティの使用</span><span class="sxs-lookup"><span data-stu-id="3dcef-102">Using the Pick Activity</span></span>
<span data-ttu-id="3dcef-103">このサンプルでは、<xref:System.Activities.Statements.Pick> アクティビティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="3dcef-104"><xref:System.Activities.Statements.Pick> アクティビティでは、イベント ベースの制御モデリングを提供します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="3dcef-105">このアクティビティの動作は C# の `switch` ステートメントに似ています。`switch` ステートメントでは、その分岐のうち 1 つだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3dcef-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="3dcef-106">ただし、値に基づいて分岐が実行される `switch` ステートメントと異なり、<xref:System.Activities.Statements.Pick> アクティビティでは、アクティビティの完了の状態に基づいて分岐を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="3dcef-107">このサンプルでは、指定した時間内にコンソールでユーザー名を入力するようユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="3dcef-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="3dcef-108">このサンプルの <xref:System.Activities.Statements.Pick> アクティビティには、ユーザーが 5 秒以内にユーザー名を入力したかどうかに基づいて実行される 2 つの分岐があります。</span><span class="sxs-lookup"><span data-stu-id="3dcef-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="3dcef-109">ユーザーが 5 秒以内にユーザー名を入力した場合は、カスタムの `ReadLine` アクティビティを含む最初の分岐が実行されます。それ以外の場合は、<xref:System.Activities.Statements.Delay> アクティビティを含むもう 1 つの分岐が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3dcef-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="3dcef-110">コンソールでユーザー名を入力すると、そのユーザー名がコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="3dcef-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="3dcef-111">5 秒以内に入力しないと、操作はタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="3dcef-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3dcef-112">使用例</span><span class="sxs-lookup"><span data-stu-id="3dcef-112">Demonstrates</span></span>
 <span data-ttu-id="3dcef-113"><xref:System.Activities.Statements.Pick> アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="3dcef-113"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="3dcef-114">説明</span><span class="sxs-lookup"><span data-stu-id="3dcef-114">Discussion</span></span>
 <span data-ttu-id="3dcef-115">このサンプルには、デザイナー ワークフローとコード化されたワークフローがあります。</span><span class="sxs-lookup"><span data-stu-id="3dcef-115">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="3dcef-116">デザイナーのワークフローのデザイナー バージョンのサンプルでは、デザイナーでワークフローを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-116">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="3dcef-117">次のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="3dcef-117">The following files are included:</span></span>

- <span data-ttu-id="3dcef-118">Program.cs:含まれています、`Main`サンプル ワークフローを実行する関数。</span><span class="sxs-lookup"><span data-stu-id="3dcef-118">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="3dcef-119">Readstring.cs:コンソールからいくつかの入力を読み取るカスタム アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="3dcef-119">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="3dcef-120">Sequence1.xaml:Pick を使用するデザイナーを使用して作成されたワークフローです。</span><span class="sxs-lookup"><span data-stu-id="3dcef-120">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="3dcef-121">コード化されたワークフロー コード化されたバージョンのサンプルでは、デザイナーでワークフローを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-121">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="3dcef-122">次のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="3dcef-122">The following files are included:</span></span>

- <span data-ttu-id="3dcef-123">Program.cs:含まれています、`Main`サンプル ワークフローを実行する関数。</span><span class="sxs-lookup"><span data-stu-id="3dcef-123">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="3dcef-124">Readstring.cs:コンソールからいくつかの入力を読み取るカスタム アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="3dcef-124">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="3dcef-125">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="3dcef-125">To use this sample</span></span>

1. <span data-ttu-id="3dcef-126">Visual Studio 2010 を使用して、Pick.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3dcef-126">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="3dcef-127">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-127">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="3dcef-128">ソリューションを実行するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3dcef-128">To run the solution, press F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="3dcef-129">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3dcef-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3dcef-130">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3dcef-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3dcef-131">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="3dcef-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3dcef-132">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3dcef-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
---
title: 実行時における DynamicActivity を使用したアクティビティの作成
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: ed133e972caa9a3a62ab2ac1310cb1bd666947ce
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321232"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="cf80f-102">実行時における DynamicActivity を使用したアクティビティの作成</span><span class="sxs-lookup"><span data-stu-id="cf80f-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<xref:System.Activities.DynamicActivity> <span data-ttu-id="cf80f-103">パブリック コンス トラクターを持つ具象、シール クラスです。</span><span class="sxs-lookup"><span data-stu-id="cf80f-103">is a concrete, sealed class with a public constructor.</span></span> <xref:System.Activities.DynamicActivity> <span data-ttu-id="cf80f-104">時にアクティビティ DOM を使用してアクティビティ機能を構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-104">can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="cf80f-105">DynamicActivity の機能</span><span class="sxs-lookup"><span data-stu-id="cf80f-105">DynamicActivity Features</span></span>  
 <xref:System.Activities.DynamicActivity> <span data-ttu-id="cf80f-106">実行プロパティの引数と変数へのアクセスが子アクティビティのスケジュール設定や追跡などのランタイム サービスにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="cf80f-106">has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="cf80f-107">最上位のプロパティは、ワークフローの <xref:System.Activities.Argument> オブジェクトを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="cf80f-108">命令型コードでは、これらの引数は新しい型で CLR プロパティを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="cf80f-109">XAML では `x:Class` タグおよび `x:Member` タグを使用して、これらの引数が宣言されます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="cf80f-110"><xref:System.Activities.DynamicActivity> を使用して構築されたアクティビティは、<xref:System.ComponentModel.ICustomTypeDescriptor> を使用してデザイナーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="cf80f-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="cf80f-111">デザイナーで作成されたアクティビティは、次の手順に示すように、<xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> を使用して動的に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="cf80f-112">命令型コードを使用して実行時にアクティビティを作成するには</span><span class="sxs-lookup"><span data-stu-id="cf80f-112">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="cf80f-113">OpenVisual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="cf80f-113">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="cf80f-114">選択**ファイル**、**新しい**、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="cf80f-115">選択**Workflow 4.0**  **Visual c#** で、**プロジェクトの種類**ウィンドウ、および選択、 **v2010**ノード。</span><span class="sxs-lookup"><span data-stu-id="cf80f-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="cf80f-116">選択**シーケンシャル ワークフロー コンソール アプリケーション**で、**テンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cf80f-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="cf80f-117">新しいプロジェクトに DynamicActivitySample という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-117">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="cf80f-118">HelloActivity プロジェクトの Workflow1.xaml を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="cf80f-119">Program.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-119">Open Program.cs.</span></span> <span data-ttu-id="cf80f-120">次のディレクティブをファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-120">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="cf80f-121">1 つの `Main` アクティビティを含む <xref:System.Activities.Statements.Sequence> アクティビティを作成する次のコードで <xref:System.Activities.Statements.WriteLine> メソッドの内容を置き換え、新しい動的アクティビティの <xref:System.Activities.DynamicActivity.Implementation%2A> プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. <span data-ttu-id="cf80f-122">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-122">Execute the application.</span></span> <span data-ttu-id="cf80f-123">コンソール ウィンドウにテキスト"Hello World!"</span><span class="sxs-lookup"><span data-stu-id="cf80f-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="cf80f-124">表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="cf80f-125">XAML を使用して実行時にアクティビティを作成するには</span><span class="sxs-lookup"><span data-stu-id="cf80f-125">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="cf80f-126">Visual Studio 2010 を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-126">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="cf80f-127">選択**ファイル**、**新しい**、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="cf80f-128">選択**Workflow 4.0**  **Visual c#** で、**プロジェクトの種類**ウィンドウ、および選択、 **v2010**ノード。</span><span class="sxs-lookup"><span data-stu-id="cf80f-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="cf80f-129">選択**ワークフロー コンソール アプリケーション**で、**テンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cf80f-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="cf80f-130">新しいプロジェクトに DynamicActivitySample という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-130">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="cf80f-131">HelloActivity プロジェクトの Workflow1.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="cf80f-132">をクリックして、**引数**デザイナーの下部にあるオプション。</span><span class="sxs-lookup"><span data-stu-id="cf80f-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="cf80f-133">`String` 型の `TextToWrite` という新しい `In` 引数を作成します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="cf80f-134">ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**デザイナー画面には、ツールボックスのセクション。</span><span class="sxs-lookup"><span data-stu-id="cf80f-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="cf80f-135">値を割り当てる`TextToWrite`を**テキスト**アクティビティのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cf80f-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="cf80f-136">Program.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-136">Open Program.cs.</span></span> <span data-ttu-id="cf80f-137">次のディレクティブをファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-137">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="cf80f-138">`Main` メソッドの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="cf80f-139">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-139">Execute the application.</span></span> <span data-ttu-id="cf80f-140">コンソール ウィンドウにテキスト"Hello World!"</span><span class="sxs-lookup"><span data-stu-id="cf80f-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="cf80f-141">表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf80f-141">appears.</span></span>  
  
8. <span data-ttu-id="cf80f-142">Workflow1.xaml ファイルを右クリックし、**ソリューション エクスプ ローラー**選択**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="cf80f-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="cf80f-143">アクティビティ クラスが `x:Class` を使用して作成され、プロパティが `x:Property` を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="cf80f-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf80f-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf80f-144">See also</span></span>

- [<span data-ttu-id="cf80f-145">命令型コードを使用してワークフロー、アクティビティ、および式を作成する方法</span><span class="sxs-lookup"><span data-stu-id="cf80f-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)

---
title: アクティビティ拡張機能の使用
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: e524f7e7127eb215be85b0c317474eee70830c2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768963"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="46da7-102">アクティビティ拡張機能の使用</span><span class="sxs-lookup"><span data-stu-id="46da7-102">Using Activity Extensions</span></span>
<span data-ttu-id="46da7-103">アクティビティは、ワークフローで明示的にモデル化されていない追加機能の提供をホストに許可するワークフロー アプリケーション拡張機能と相互作用することができます。</span><span class="sxs-lookup"><span data-stu-id="46da7-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="46da7-104">ここでは、アクティビティの実行回数をカウントする拡張機能を作成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="46da7-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>

### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="46da7-105">実行回数をカウントするアクティビティ拡張機能を使用するには</span><span class="sxs-lookup"><span data-stu-id="46da7-105">To use an activity extension to count executions</span></span>

1. <span data-ttu-id="46da7-106">Visual Studio 2010 を開きます。</span><span class="sxs-lookup"><span data-stu-id="46da7-106">Open Visual Studio 2010.</span></span> <span data-ttu-id="46da7-107">選択**新しい**、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="46da7-107">Select **New**, **Project**.</span></span> <span data-ttu-id="46da7-108">下、 **Visual c#** ノードの **ワークフロー**します。</span><span class="sxs-lookup"><span data-stu-id="46da7-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="46da7-109">選択**ワークフロー コンソール アプリケーション**テンプレートの一覧から。</span><span class="sxs-lookup"><span data-stu-id="46da7-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="46da7-110">プロジェクトに `Extensions` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="46da7-110">Name the project `Extensions`.</span></span> <span data-ttu-id="46da7-111">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="46da7-111">Click **OK** to create the project.</span></span>

2. <span data-ttu-id="46da7-112">追加、`using`の Program.cs ファイル内のステートメント、 **System.Collections.Generic**名前空間。</span><span class="sxs-lookup"><span data-stu-id="46da7-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>

    ```
    using System.Collections.Generic;
    ```

3. <span data-ttu-id="46da7-113">という名前の新しいクラスを作成、Program.cs ファイルで**ExecutionCountExtension**します。</span><span class="sxs-lookup"><span data-stu-id="46da7-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="46da7-114">次のコードでは、インスタンス Id を追跡するワークフロー拡張機能とその**登録**メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46da7-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>

    ```
    // This extension collects a list of workflow Ids
    public class ExecutionCountExtension
    {
        IList<Guid> instances = new List<Guid>();

        public int ExecutionCount
        {
            get
            {
                return this.instances.Count;
            }
        }

        public IEnumerable<Guid> InstanceIds
        {
            get
            {
                return this.instances;
            }
        }

        public void Register(Guid activityInstanceId)
        {
            if (!this.instances.Contains<Guid>(activityInstanceId))
            {
                instances.Add(activityInstanceId);
            }
        }
    }
    ```

4. <span data-ttu-id="46da7-115">使用するアクティビティを作成、 **ExecutionCountExtension**します。</span><span class="sxs-lookup"><span data-stu-id="46da7-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="46da7-116">次のコードを取得するアクティビティを定義する、 **ExecutionCountExtension**オブジェクトを実行時と呼び出しからその**登録**アクティビティの実行時のメソッド。</span><span class="sxs-lookup"><span data-stu-id="46da7-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>

    ```
    // Activity that consumes an extension provided by the host. If the extension is available
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)
    public class MyActivity: CodeActivity
    {
        protected override void Execute(CodeActivityContext context)
        {
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();
            if (ext != null)
            {
                ext.Register(context.WorkflowInstanceId);
            }

        }
    }
    ```

5. <span data-ttu-id="46da7-117">アクティビティでは、実装、 **Main** program.cs ファイルのメソッド。</span><span class="sxs-lookup"><span data-stu-id="46da7-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="46da7-118">次のコードには、2 つの異なるワークフローを生成し、各ワークフローを数回実行して、拡張機能に含まれる結果のデータを表示するメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46da7-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>

    ```
    class Program
    {
        // Creates a workflow that uses the activity that consumes the extension
        static Activity CreateWorkflow1()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity()
                }
            };
        }

        // Creates a workflow that uses two instances of the activity that consumes the extension
        static Activity CreateWorkflow2()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity(),
                    new MyActivity()
                }
            };
        }

        static void Main(string[] args)
        {
            // create the extension
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();

            // configure the first invoker and execute 3 times
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());
            invoker.Extensions.Add(executionCountExt);
            invoker.Invoke();
            invoker.Invoke();
            invoker.Invoke();

            // configure the second invoker and execute 2 times
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());
            invoker2.Extensions.Add(executionCountExt);
            invoker2.Invoke();
            invoker2.Invoke();

            // show the data in the extension
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));
        }
    }
    ```

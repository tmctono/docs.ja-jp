---
title: C# の式
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: c50f6a2a8dfb69b914fb4fa84c028f9d65c00cfa
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882098"
---
# <a name="c-expressions"></a><span data-ttu-id="89acd-102">C# の式</span><span class="sxs-lookup"><span data-stu-id="89acd-102">C# Expressions</span></span>
<span data-ttu-id="89acd-103">以降で[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、c# 式には、Windows Workflow Foundation (WF) ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-103">Starting with [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="89acd-104">Visual Studio 2012 を対象に作成された新しい c# ワークフロー プロジェクト[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]c# 式を使用、および Visual Basic ワークフロー プロジェクトが Visual Basic 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="89acd-104">New C# workflow projects created in Visual Studio 2012 that target [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="89acd-105">Visual Basic 式を使用する既存の [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] ワークフロー プロジェクトは、プロジェクトの言語に関係なく [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] に移行することができ、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-105">Existing [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="89acd-106">ここでは、[!INCLUDE[wf1](../../../includes/wf1-md.md)] での C# 式の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="89acd-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="89acd-107">ワークフローでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-107">Using C# expressions in workflows</span></span>

- [<span data-ttu-id="89acd-108">ワークフロー デザイナーで c# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-108">Using C# expressions in the Workflow Designer</span></span>](csharp-expressions.md#WFDesigner)

    - [<span data-ttu-id="89acd-109">下位互換性</span><span class="sxs-lookup"><span data-stu-id="89acd-109">Backwards compatibility</span></span>](csharp-expressions.md#BackwardCompat)

- [<span data-ttu-id="89acd-110">コード ワークフローでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-110">Using C# expressions in code workflows</span></span>](csharp-expressions.md#CodeWorkflows)

- [<span data-ttu-id="89acd-111">XAML ワークフローでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-111">Using C# expressions in XAML workflows</span></span>](csharp-expressions.md#XamlWorkflows)

    - [<span data-ttu-id="89acd-112">コンパイルされた Xaml</span><span class="sxs-lookup"><span data-stu-id="89acd-112">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

    - [<span data-ttu-id="89acd-113">Loose Xaml</span><span class="sxs-lookup"><span data-stu-id="89acd-113">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

- [<span data-ttu-id="89acd-114">XAMLX ワークフロー サービスでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-114">Using C# expressions in XAMLX workflow services</span></span>](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a> <span data-ttu-id="89acd-115">ワークフロー デザイナーで c# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-115">Using C# expressions in the Workflow Designer</span></span>
 <span data-ttu-id="89acd-116">以降で[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、c# 式には、Windows Workflow Foundation (WF) ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-116">Starting with [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="89acd-117">Visual Studio 2012 を対象に作成された c# ワークフロー プロジェクト[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]の c# 式を使用して、Visual Basic ワークフロー プロジェクトは Visual Basic 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="89acd-117">C# workflow projects created in Visual Studio 2012 that target [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="89acd-118">必要な c# の式を指定するというラベルの付いたボックスに入力**c# 式を入力します**します。</span><span class="sxs-lookup"><span data-stu-id="89acd-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="89acd-119">このラベルは、プロパティ ウィンドウ (デザイナーでアクティビティを選択した場合) またはワークフロー デザイナーのアクティビティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="89acd-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="89acd-120">次の例では、2 つの `WriteLine` アクティビティが `Sequence` の中で `NoPersistScope` 内に含まれています。</span><span class="sxs-lookup"><span data-stu-id="89acd-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

 ![自動的に作成されたシーケンス アクティビティを示すスクリーン ショット。](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
>  <span data-ttu-id="89acd-122">C# 式は、Visual Studio でのみサポートされ、再ホストされたワークフロー デザイナーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="89acd-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="89acd-123">再ホストされたデザイナーでサポートされている新しい WF45 の機能の詳細については、次を参照してください。[再ホストされたワークフロー デザイナーでの新しい Workflow Foundation 4.5 機能のサポート](wf-features-in-the-rehosted-workflow-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="89acd-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md).</span></span>

#### <a name="BackwardCompat"></a> <span data-ttu-id="89acd-124">下位互換性</span><span class="sxs-lookup"><span data-stu-id="89acd-124">Backwards compatibility</span></span>
 <span data-ttu-id="89acd-125">
  [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] に移行した既存の [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] C# ワークフロー プロジェクトの Visual Basic 式はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-125">Visual Basic expressions in existing [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="89acd-126">Visual Basic 式をワークフロー デザイナーで表示すると、既存の Visual Basic の式のテキストが置き換え**値は、XAML で設定された**Visual Basic の式が有効な c# 構文でない限り、します。</span><span class="sxs-lookup"><span data-stu-id="89acd-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="89acd-127">Visual Basic 式が有効な C# 構文である場合は、式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="89acd-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="89acd-128">Visual Basic 式を C# に更新するには、ワークフロー デザイナーでその式を編集して、対応する C# 式を指定します。</span><span class="sxs-lookup"><span data-stu-id="89acd-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="89acd-129">Visual Basic 式を C# に更新する必要はありませんが、ワークフロー デザイナーで式を更新すると、式は C# に変換され、Visual Basic に戻すことができなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="89acd-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

### <a name="CodeWorkflows"></a> <span data-ttu-id="89acd-130">コード ワークフローでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-130">Using C# expressions in code workflows</span></span>
 <span data-ttu-id="89acd-131">C# 式は、[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] コードベースのワークフローでサポートされていますが、ワークフローを呼び出す前に、<xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType> を使用して C# 式をコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89acd-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="89acd-132">ワークフローの作成者は、`CSharpValue` を使用して式の右辺値を表し、`CSharpReference` を使用して式の左辺値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="89acd-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="89acd-133">次の例では、`Assign` アクティビティに含まれる `WriteLine` アクティビティと `Sequence` アクティビティを使用してワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="89acd-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="89acd-134">`CSharpReference` は `To` の `Assign` 引数として指定され、式の左辺値を表します。</span><span class="sxs-lookup"><span data-stu-id="89acd-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="89acd-135">`CSharpValue` は `Value` の `Assign` 引数、および `Text` の `WriteLine` 引数として指定され、2 つの式の右辺値を表します。</span><span class="sxs-lookup"><span data-stu-id="89acd-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

 <span data-ttu-id="89acd-136">ワークフローが作成されると、`CompileExpressions` ヘルパー メソッドを呼び出して C# 式がコンパイルされ、ワークフローが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="89acd-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="89acd-137">次の例は、`CompileExpressions` メソッドです。</span><span class="sxs-lookup"><span data-stu-id="89acd-137">The following example is the `CompileExpressions` method.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
>  <span data-ttu-id="89acd-138">場合、C#式がコンパイルされない、 <xref:System.NotSupportedException> 、次のようなメッセージでワークフローが呼び出される場合にスローされます。`Expression Activity type 'CSharpValue`1' を実行するためにコンパイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="89acd-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="89acd-139">ワークフローがコンパイルされていることを確認してください '。</span><span class="sxs-lookup"><span data-stu-id="89acd-139">Please ensure that the workflow has been compiled.\`</span></span>

 <span data-ttu-id="89acd-140">カスタムのコードベースのワークフローで `DynamicActivity` を使用する場合は、次のコード例に示すように、`CompileExpressions` メソッドに変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="89acd-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

 <span data-ttu-id="89acd-141">動的アクティビティで C# 式をコンパイルする `CompileExpressions` オーバーロードには、いくつかの相違点があります。</span><span class="sxs-lookup"><span data-stu-id="89acd-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

- <span data-ttu-id="89acd-142">`CompileExpressions` のパラメーターが `DynamicActivity` です。</span><span class="sxs-lookup"><span data-stu-id="89acd-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

- <span data-ttu-id="89acd-143">型名および名前空間の取得に `DynamicActivity.Name` プロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="89acd-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

- <span data-ttu-id="89acd-144">`TextExpressionCompilerSettings.ForImplementation` が `true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="89acd-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

- <span data-ttu-id="89acd-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` の代わりに `CompiledExpressionInvoker.SetCompiledExpressionRoot` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="89acd-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

 <span data-ttu-id="89acd-146">コード内の式の使用方法の詳細については、次を参照してください。[オーサリング ワークフロー、アクティビティ、および命令型コードを使用して式](authoring-workflows-activities-and-expressions-using-imperative-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="89acd-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

### <a name="XamlWorkflows"></a> <span data-ttu-id="89acd-147">XAML ワークフローでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-147">Using C# expressions in XAML workflows</span></span>
 <span data-ttu-id="89acd-148">C# 式は XAML ワークフローでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="89acd-149">コンパイルされた XAML ワークフローは型にコンパイルされ、Loose XAML ワークフローはランタイムによって読み込まれ、ワークフローの実行時にアクティビティ ツリーにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="89acd-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

- [<span data-ttu-id="89acd-150">コンパイルされた Xaml</span><span class="sxs-lookup"><span data-stu-id="89acd-150">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

- [<span data-ttu-id="89acd-151">Loose Xaml</span><span class="sxs-lookup"><span data-stu-id="89acd-151">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a> <span data-ttu-id="89acd-152">コンパイルされた Xaml</span><span class="sxs-lookup"><span data-stu-id="89acd-152">Compiled Xaml</span></span>
 <span data-ttu-id="89acd-153">C# 式は、コンパイルされた XAML ワークフローでサポートされており、[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] を対象とする C# ワークフロー プロジェクトの一部として型にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="89acd-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="89acd-154">コンパイルされた XAML、Visual Studio で、ワークフローの作成の既定の型とで作成された c# ワークフロー プロジェクト Visual Studio を対象とする[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]c# 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="89acd-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

#### <a name="LooseXaml"></a> <span data-ttu-id="89acd-155">Loose Xaml</span><span class="sxs-lookup"><span data-stu-id="89acd-155">Loose Xaml</span></span>
 <span data-ttu-id="89acd-156">C# 式は Loose XAML ワークフローでがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="89acd-157">Loose XAML ワークフローを読み込んで呼び出すワークフロー ホスト プログラムは、[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] を対象としている必要があります。また、<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> は `true` (既定値は `false`) に設定する必要がります。</span><span class="sxs-lookup"><span data-stu-id="89acd-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="89acd-158">
  <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> を `true\` に設定するには、<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> プロパティが <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> に設定されている `true\` インスタンスを作成し、そのインスタンスを <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType> へパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="89acd-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="89acd-159">場合`CompileExpressions`に設定されていない`true`、<xref:System.NotSupportedException>次のようなメッセージがスローされます。`Expression Activity type 'CSharpValue`1' を実行するためにコンパイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="89acd-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="89acd-160">ワークフローがコンパイルされていることを確認してください '。</span><span class="sxs-lookup"><span data-stu-id="89acd-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

 <span data-ttu-id="89acd-161">XAML ワークフローを使った操作の詳細については、次を参照してください。[ワークフローのシリアル化と XAML との間のアクティビティ](serializing-workflows-and-activities-to-and-from-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="89acd-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

### <a name="WFServices"></a> <span data-ttu-id="89acd-162">XAMLX ワークフロー サービスでの C# 式の使用</span><span class="sxs-lookup"><span data-stu-id="89acd-162">Using C# expressions in XAMLX workflow services</span></span>
 <span data-ttu-id="89acd-163">C# 式は XAMLX ワークフロー サービスでがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89acd-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="89acd-164">ワークフロー サービスが IIS または WAS でホストされている場合、追加の手順は必要ありません。ただし、XAML ワークフロー サービスが自己ホスト型サービスの場合は、C# 式をコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89acd-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="89acd-165">自己ホスト型の XAMLX ワークフロー サービス内の c# 式をコンパイルするには、最初に XAMLX ファイルを読み込む、 `WorkflowService`、し、渡します、`Body`の`WorkflowService`を`CompileExpressions`メソッドの前で説明されている[c# を使用しました。コード ワークフローで式](csharp-expressions.md#CodeWorkflows)セクション。</span><span class="sxs-lookup"><span data-stu-id="89acd-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="89acd-166">次の例では、XAMLX ワークフロー サービスが読み込まれ、C# 式がコンパイルされた後、ワークフロー サービスが開かれて要求を待機します。</span><span class="sxs-lookup"><span data-stu-id="89acd-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

 <span data-ttu-id="89acd-167">C# 式がコンパイルされないと、`Open` の処理は成功しますが、ワークフローは呼び出し時に失敗します。</span><span class="sxs-lookup"><span data-stu-id="89acd-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="89acd-168">次`CompileExpressions`メソッドは、前のメソッドと同じ[コード ワークフローで c# を使用した式](csharp-expressions.md#CodeWorkflows)セクション。</span><span class="sxs-lookup"><span data-stu-id="89acd-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

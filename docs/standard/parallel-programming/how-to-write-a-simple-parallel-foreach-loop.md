---
title: Parallel.ForEach を使用して単純な並列プログラムを記述する
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 02b94b673dc4468e68a1dadd83aab0e3bfcfaa16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160301"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="101b6-102">方法: 単純な Parallel.ForEach ループを記述する</span><span class="sxs-lookup"><span data-stu-id="101b6-102">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="101b6-103">この例は、<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> ループを使用して、<xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> データ ソースでのデータの並列処理を有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="101b6-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="101b6-104">ここでは、ラムダ式を使用して PLINQ でデリゲートを定義します。</span><span class="sxs-lookup"><span data-stu-id="101b6-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="101b6-105">C# または Visual Basic のラムダ式についての情報が必要な場合は、「[PLINQ および TPL のラムダ式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101b6-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="101b6-106">例</span><span class="sxs-lookup"><span data-stu-id="101b6-106">Example</span></span>

<span data-ttu-id="101b6-107">この例では、*C:\Users\Public\Pictures\Sample Pictures* フォルダーにいくつかの .jpg ファイルがあることを想定し、*Modified* という名前の新しいサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="101b6-107">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="101b6-108">例を実行すると、*Sample Pictures* のそれぞれの .jpg 画像が回転して、*Modified* に保存されます。</span><span class="sxs-lookup"><span data-stu-id="101b6-108">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="101b6-109">2 つのパスは必要に応じて変更することができます。</span><span class="sxs-lookup"><span data-stu-id="101b6-109">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="101b6-110"><xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> ループは <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> ループのように動作します。</span><span class="sxs-lookup"><span data-stu-id="101b6-110">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="101b6-111">ループによってソース コレクションがパーティション分割され、作業はシステム環境に基づいて複数のスレッドでスケジューリングされます。</span><span class="sxs-lookup"><span data-stu-id="101b6-111">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="101b6-112">システムのプロセッサの数が多いほど、並列メソッドの実行が速くなります。</span><span class="sxs-lookup"><span data-stu-id="101b6-112">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="101b6-113">一部のソース コレクションでは、ソースのサイズやループで実行される作業の種類に応じて、順次ループがより高速になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="101b6-113">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="101b6-114">パフォーマンスの詳細については、「[データとタスクの並列化における注意点](potential-pitfalls-in-data-and-task-parallelism.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101b6-114">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="101b6-115">並列ループの詳細については、「[方法: 単純な Parallel.For ループを記述する](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101b6-115">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="101b6-116">非ジェネリック コレクションで <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> を使用する場合は、次の例に示すように、<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> 拡張メソッドを使用して、コレクションをジェネリック コレクションに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="101b6-116">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="101b6-117">また、Parallel LINQ (PLINQ) を使用して、<xref:System.Collections.Generic.IEnumerable%601> データ ソースの処理を並列化することもできます。</span><span class="sxs-lookup"><span data-stu-id="101b6-117">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="101b6-118">PLINQ では、宣言型のクエリ構文を使用して、ループの動作を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="101b6-118">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="101b6-119">詳細については、「[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101b6-119">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="101b6-120">コードをコンパイルして実行する</span><span class="sxs-lookup"><span data-stu-id="101b6-120">Compile and run the code</span></span>

<span data-ttu-id="101b6-121">コードは .NET Framework のコンソール アプリケーションまたは .NET Core のコンソール アプリケーションとしてコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="101b6-121">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="101b6-122">Visual Studio には、Windows デスクトップと .NET Core 向けに、Visual Basic と C# のコンソール アプリケーション テンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="101b6-122">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="101b6-123">コマンド ラインから .NET Core CLI コマンド (`dotnet new console` や `dotnet new console -lang vb` など) を使用するか、またはファイルを作成して .NET Framework アプリケーション用のコマンド ライン コンパイラを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="101b6-123">From the command line, you can use either the .NET Core CLI commands (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="101b6-124">.NET Core プロジェクトの場合は、**System.Drawing.Common** NuGet パッケージを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101b6-124">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="101b6-125">Visual Studio ではパッケージのインストールに NuGet パッケージ マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="101b6-125">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="101b6-126">または、\*.csproj または \*.vbproj ファイルにパッケージへの参照を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="101b6-126">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="101b6-127">コマンド ラインから .NET Core コンソール アプリケーションを実行するには、アプリケーションが含まれるフォルダーから `dotnet run` を使用します。</span><span class="sxs-lookup"><span data-stu-id="101b6-127">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="101b6-128">Visual Studio からコンソール アプリケーションを実行するには、**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="101b6-128">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="101b6-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="101b6-129">See also</span></span>

- [<span data-ttu-id="101b6-130">データの並列化</span><span class="sxs-lookup"><span data-stu-id="101b6-130">Data parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="101b6-131">並列プログラミング</span><span class="sxs-lookup"><span data-stu-id="101b6-131">Parallel programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="101b6-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="101b6-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)

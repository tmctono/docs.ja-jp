---
title: C# プログラムの構造 - C# 言語のツアー
description: C# プログラムの基本的な構造について説明します
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156832"
---
# <a name="program-structure"></a><span data-ttu-id="dc2b6-103">プログラムの構造</span><span class="sxs-lookup"><span data-stu-id="dc2b6-103">Program Structure</span></span>

<span data-ttu-id="dc2b6-104">C# における主要な組織的概念は、***プログラム***、***名前空間***、***型***、***メンバー***、および***アセンブリ***です。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="dc2b6-105">C# プログラムは、1 つまたは複数のソース ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="dc2b6-106">プログラムは型を宣言します。型にはメンバーが含まれていて、複数の名前空間に編成することができます。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="dc2b6-107">型の例には、クラスおよびインターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="dc2b6-108">メンバーの例には、フィールド、メソッド、プロパティ、およびイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="dc2b6-109">C# プログラムはコンパイルされると、物理的にアセンブリにパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="dc2b6-110">アセンブリには通常、***アプリケーション***または***ライブラリ***のどちらかを実行するかに応じて、それぞれ `.exe` または `.dll` のファイル拡張子があります。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="dc2b6-111">`dotnet new` コマンドを使用して、*acme* という名前のライブラリ プロジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```console
dotnet new classlib -o acme
```

<span data-ttu-id="dc2b6-112">そのプロジェクトでは、`Acme.Collections` という名前の名前空間で `Stack` という名前のクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="dc2b6-113">このクラスの完全修飾名は `Acme.Collections.Stack` です。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="dc2b6-114">このクラスには複数のメンバーが含まれています: `top` という名前のフィールドが 1 つ、`Push` と `Pop` という名前のメソッドが合わせて 2 つ、そして `Entry` という名前の入れ子になったクラスです。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="dc2b6-115">`Entry` クラスにはさらに、3 つのメンバーが含まれています: `next` という名前のフィールド、`data` という名前のフィールド、およびコンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="dc2b6-116">コマンド:</span><span class="sxs-lookup"><span data-stu-id="dc2b6-116">The command:</span></span>

```console
dotnet build
```

<span data-ttu-id="dc2b6-117">このコマンド ラインは例をライブラリ (`Main` エントリ ポイントがないコード) としてコンパイルし、`acme.dll` という名前のアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="dc2b6-118">アセンブリには実行可能なコードが中間言語 (IL) の形式で含まれていて、シンボル情報がメタデータの形式で含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="dc2b6-119">実行前に、.NET 共通言語ランタイムの Just-In-Time (JIT) コンパイラによって、アセンブリの IL コードはプロセッサ固有のコードに変換されます。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="dc2b6-120">アセンブリはコードとメタデータの両方を含む自己記述的な機能的単位であるため、`#include` ディレクティブおよびヘッダー ファイルを C# に含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="dc2b6-121">特定のアセンブリに含まれているパブリックの型とメンバーは、単にプログラムのコンパイル中にそのアセンブリを参照することにより、C# プログラムで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="dc2b6-122">たとえば、このプログラムでは `acme.dll` アセンブリの `Acme.Collections.Stack` クラスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="dc2b6-123">前のプログラムのプロジェクトの *.csproj* ファイルには、`acme.dll` アセンブリ内のクラスへの参照を解決するために、C# コンパイラの参照ノードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="dc2b6-124">これを追加すると、`dotnet build` によって `example.exe` という名前の実行可能なアセンブリが作成され、実行時に次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="dc2b6-125">C# では、プログラムのソース テキストを複数のソース ファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="dc2b6-126">複数ファイルの C# プログラムがコンパイルされると、ソース ファイルはすべて同時に処理され、ソース ファイルは自由に相互を参照できるようになります。概念的には、ソース ファイルが処理される前に、すべて 1 つの大きいファイルに連結されるようなものです。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="dc2b6-127">C# では事前宣言をする必要がありません。ごく一部の例外を除いて、宣言の順序は重要でないためです。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="dc2b6-128">C# ではソース ファイルがパブリック型 1 つのみの宣言に制限されません。また、ソース ファイルの名前がソース ファイルで宣言された型に一致する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="dc2b6-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc2b6-129">[前へ](index.md)
>[次へ](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="dc2b6-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>

---
description: -link (C# コンパイラ オプション)
title: -link (C# コンパイラ オプション)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 6fd291c49c282713ea56ca20d8d58616d38ec752
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465716"
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="c951f-103">-link (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="c951f-103">-link (C# Compiler Options)</span></span>
<span data-ttu-id="c951f-104">指定したアセンブリ内の COM 型情報を、現在のコンパイル対象のプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c951f-104">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>

## <a name="syntax"></a><span data-ttu-id="c951f-105">構文</span><span class="sxs-lookup"><span data-stu-id="c951f-105">Syntax</span></span>

```console
-link:fileList
// -or-
-l:fileList
```

## <a name="arguments"></a><span data-ttu-id="c951f-106">引数</span><span class="sxs-lookup"><span data-stu-id="c951f-106">Arguments</span></span>
 `fileList`  
 <span data-ttu-id="c951f-107">必須です。</span><span class="sxs-lookup"><span data-stu-id="c951f-107">Required.</span></span> <span data-ttu-id="c951f-108">アセンブリ ファイル名のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="c951f-108">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="c951f-109">ファイル名に空白が含まれている場合は、名前を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c951f-109">If the file name contains a space, enclose the name in quotation marks.</span></span>

## <a name="remarks"></a><span data-ttu-id="c951f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c951f-110">Remarks</span></span>
 <span data-ttu-id="c951f-111">`-link` オプションを使用すると、埋め込み型情報を含むアプリケーションを配置できます。</span><span class="sxs-lookup"><span data-stu-id="c951f-111">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="c951f-112">その後、このアプリケーションは、埋め込み型情報を実装する、ランタイム アセンブリ内の型を使用できます。その際、ランタイム アセンブリへの参照は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c951f-112">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="c951f-113">ランタイム アセンブリのさまざまなバージョンが公開されている場合、埋め込み型情報を含むアプリケーションは、再コンパイルする必要なく、各種バージョンで動作できます。</span><span class="sxs-lookup"><span data-stu-id="c951f-113">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="c951f-114">例については、「[チュートリアル:マネージド アセンブリからの型の埋め込み](../../../standard/assembly/embed-types-visual-studio.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c951f-114">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="c951f-115">`-link` オプションの使用は、COM 相互運用を使用している場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="c951f-115">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="c951f-116">COM 型を埋め込むことができるため、アプリケーションは、ターゲット コンピューター上にプライマリ相互運用機能アセンブリ (PIA) を必要としなくなります。</span><span class="sxs-lookup"><span data-stu-id="c951f-116">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="c951f-117">`-link` オプションを使用すると、コンパイラによって、COM 型情報は、参照先の相互運用アセンブリから結果としてコンパイルされるコードに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="c951f-117">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="c951f-118">COM 型は、CLSID (GUID) 値によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="c951f-118">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="c951f-119">その結果、同じ CLSID 値の同じ COM 型がインストールされているターゲット コンピューターでアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c951f-119">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="c951f-120">Microsoft Office を自動化するアプリケーションが良い例です。</span><span class="sxs-lookup"><span data-stu-id="c951f-120">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="c951f-121">Office のようなアプリケーションは、通常、さまざまなバージョン間で同じ CLSID 値を保持するため、.NET Framework 4 以降がターゲット コンピューターにインストールされていて、参照先の COM 型に含まれているメソッド、プロパティ、またはイベントがアプリケーションで使用される限りは、そのアプリケーションで参照先の COM 型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c951f-121">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>

 <span data-ttu-id="c951f-122">`-link` オプションで埋め込まれるのは、インターフェイス、構造体、デリゲートのみです。</span><span class="sxs-lookup"><span data-stu-id="c951f-122">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="c951f-123">COM クラスの埋め込みはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c951f-123">Embedding COM classes is not supported.</span></span>

> [!NOTE]
> <span data-ttu-id="c951f-124">コードで埋め込み COM 型のインスタンスを作成する際は、適切なインターフェイスを使用してインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c951f-124">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="c951f-125">コクラスを使用して埋め込み COM 型のインスタンスを作成しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c951f-125">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>

 <span data-ttu-id="c951f-126">Visual Studio で `-link` オプションを設定するには、アセンブリ参照を追加し、`Embed Interop Types` プロパティを **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c951f-126">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="c951f-127">`Embed Interop Types` プロパティの既定値は **false** です。</span><span class="sxs-lookup"><span data-stu-id="c951f-127">The default for the `Embed Interop Types` property is **false**.</span></span>

 <span data-ttu-id="c951f-128">別の COM アセンブリ (アセンブリ B) を参照する COM アセンブリ (アセンブリ A) にリンクする場合、次のいずれかが当てはまるときは、アセンブリ B にもリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c951f-128">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>

- <span data-ttu-id="c951f-129">アセンブリ A の型がアセンブリ B の型から継承されているか、アセンブリ B のインターフェイスを実装する。</span><span class="sxs-lookup"><span data-stu-id="c951f-129">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>

- <span data-ttu-id="c951f-130">アセンブリ B の戻り値の型またはパラメーターの型を使用するフィールド、プロパティ、イベント、またはメソッドが呼び出される。</span><span class="sxs-lookup"><span data-stu-id="c951f-130">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>

 <span data-ttu-id="c951f-131">[-reference](./reference-compiler-option.md) コンパイラ オプションと同様、`-link` コンパイラ オプションでは、使用頻度の高い .NET アセンブリを参照する Csc.rsp 応答ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c951f-131">Like the [-reference](./reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used .NET assemblies.</span></span> <span data-ttu-id="c951f-132">コンパイラで Csc.rsp ファイルを使用しない場合は、[-noconfig](./noconfig-compiler-option.md) コンパイラ オプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c951f-132">Use the [-noconfig](./noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>

 <span data-ttu-id="c951f-133">`-link` の省略形は `-l` です。</span><span class="sxs-lookup"><span data-stu-id="c951f-133">The short form of `-link` is `-l`.</span></span>

## <a name="generics-and-embedded-types"></a><span data-ttu-id="c951f-134">ジェネリック型と埋め込み型</span><span class="sxs-lookup"><span data-stu-id="c951f-134">Generics and Embedded Types</span></span>
 <span data-ttu-id="c951f-135">以降のセクションでは、相互運用機能型を埋め込むアプリケーションでジェネリック型を使用する際の制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="c951f-135">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>

### <a name="generic-interfaces"></a><span data-ttu-id="c951f-136">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c951f-136">Generic Interfaces</span></span>
 <span data-ttu-id="c951f-137">相互運用アセンブリから埋め込まれるジェネリック インターフェイスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c951f-137">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="c951f-138">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c951f-138">This is shown in the following example.</span></span>

 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]

### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="c951f-139">ジェネリック パラメーターを含む型</span><span class="sxs-lookup"><span data-stu-id="c951f-139">Types That Have Generic Parameters</span></span>
 <span data-ttu-id="c951f-140">型が相互運用アセンブリから埋め込まれているジェネリック パラメーターを含む型は、外部アセンブリからの型である場合に使用できません。</span><span class="sxs-lookup"><span data-stu-id="c951f-140">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="c951f-141">この制限はインターフェイスには当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="c951f-141">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="c951f-142">たとえば、<xref:Microsoft.Office.Interop.Excel> アセンブリで定義されている <xref:Microsoft.Office.Interop.Excel.Range> インターフェイスについて考えます。</span><span class="sxs-lookup"><span data-stu-id="c951f-142">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="c951f-143">ライブラリによって <xref:Microsoft.Office.Interop.Excel> アセンブリから相互運用型が埋め込まれ、型が <xref:Microsoft.Office.Interop.Excel.Range> インターフェイスであるパラメーターを含むジェネリック型を返すメソッドが公開される場合、次のコード例に示すように、そのメソッドはジェネリック インターフェイスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c951f-143">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>

[!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs)]

 <span data-ttu-id="c951f-144">次の例では、クライアント コードで、<xref:System.Collections.IList> ジェネリック インターフェイスを返すメソッドをエラーなしで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c951f-144">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>

 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]

## <a name="example"></a><span data-ttu-id="c951f-145">例</span><span class="sxs-lookup"><span data-stu-id="c951f-145">Example</span></span>
 <span data-ttu-id="c951f-146">次のコードは、ソース ファイル `OfficeApp.cs` と、`COMData1.dll` および `COMData2.dll` からの参照アセンブリをコンパイルして、`OfficeApp.exe` を生成します。</span><span class="sxs-lookup"><span data-stu-id="c951f-146">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>

```csharp
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs
```

## <a name="see-also"></a><span data-ttu-id="c951f-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="c951f-147">See also</span></span>

- [<span data-ttu-id="c951f-148">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="c951f-148">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c951f-149">チュートリアル: マネージド アセンブリからの型の埋め込み</span><span class="sxs-lookup"><span data-stu-id="c951f-149">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="c951f-150">-reference (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="c951f-150">-reference (C# Compiler Options)</span></span>](./reference-compiler-option.md)
- [<span data-ttu-id="c951f-151">-noconfig (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="c951f-151">-noconfig (C# Compiler Options)</span></span>](./noconfig-compiler-option.md)
- [<span data-ttu-id="c951f-152">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="c951f-152">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
- [<span data-ttu-id="c951f-153">相互運用性の概要</span><span class="sxs-lookup"><span data-stu-id="c951f-153">Interoperability Overview</span></span>](../../programming-guide/interop/interoperability-overview.md)

---
title: 'How to: Build a multifile assembly'
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: 0f8c6d57425657e321d80f9edffa20f27bc28770
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429559"
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="5e77e-102">How to: Build a multifile assembly</span><span class="sxs-lookup"><span data-stu-id="5e77e-102">How to: Build a multifile assembly</span></span>

<span data-ttu-id="5e77e-103">この記事では、マルチファイル アセンブリを作成する方法を説明し、プロシージャの各手順を示すコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="5e77e-104">Visual Studio IDE for C# および Visual Basic は、シングルファイル アセンブリの作成でしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="5e77e-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="5e77e-105">マルチファイル アセンブリを作成する場合は、コマンド ライン コンパイラまたは Visual C++ 付き Visual Studio を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e77e-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="5e77e-106">マルチファイル アセンブリは .NET Framework でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-106">Multifile assemblies are supported by .NET Framework only.</span></span>

## <a name="create-a-multifile-assembly"></a><span data-ttu-id="5e77e-107">マルチファイル アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="5e77e-107">Create a multifile assembly</span></span>

1. <span data-ttu-id="5e77e-108">アセンブリ内のほかのモジュールによって参照される名前空間を含むすべてのファイルをコンパイルして、コード モジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-108">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="5e77e-109">コード モジュールの既定の拡張子は *.netmodule* です。</span><span class="sxs-lookup"><span data-stu-id="5e77e-109">The default extension for code modules is *.netmodule*.</span></span>

   <span data-ttu-id="5e77e-110">たとえば、`Stringer` ファイルに `myStringer` と呼ばれるクラスを含む `Stringer` という名前空間があるとします。</span><span class="sxs-lookup"><span data-stu-id="5e77e-110">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="5e77e-111">`Stringer` クラスには、コンソールに 1 つの行を書き込む `StringerMethod` メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-111">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. <span data-ttu-id="5e77e-112">このコードをコンパイルするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-112">Use the following command to compile this code:</span></span>

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   <span data-ttu-id="5e77e-113">*module* パラメーターと **/t:** コンパイラ オプションを指定すると、ファイルはアセンブリではなくモジュールとしてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-113">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="5e77e-114">コンパイラにより、アセンブリに追加できる *Stringer.netmodule* というモジュールが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-114">The compiler produces a module called *Stringer.netmodule*, which can be added to an assembly.</span></span>

3. <span data-ttu-id="5e77e-115">コード内で参照されるほかのモジュールを示すために必要なコンパイラ オプションを使用して、ほかのすべてのモジュールをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="5e77e-115">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="5e77e-116">この手順では、 **/addmodule** コンパイラ オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-116">This step uses the **/addmodule** compiler option.</span></span>

   <span data-ttu-id="5e77e-117">次の例では、*Client* というコード モジュールに、手順 1. で作成した *Stringer.dll* モジュール内のメソッドを参照するエントリ ポイント `Main` メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="5e77e-117">In the following example, a code module called *Client* has an entry point `Main` method that references a method in the *Stringer.dll* module created in step 1.</span></span>

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. <span data-ttu-id="5e77e-118">このコードをコンパイルするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-118">Use the following command to compile this code:</span></span>

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   <span data-ttu-id="5e77e-119">このモジュールは後の手順でアセンブリに追加するため、 **/t:module** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-119">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="5e77e-120">*Client* 内のコードが *Stringer.netmodule* 内のコードによって作成された名前空間を参照するため、 **/addmodule** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-120">Specify the **/addmodule** option because the code in *Client* references a namespace created by the code in *Stringer.netmodule*.</span></span> <span data-ttu-id="5e77e-121">コンパイラにより、*Stringer.netmodule* という別のモジュールへの参照を格納する、*Client.netmodule* というモジュールが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-121">The compiler produces a module called *Client.netmodule* that contains a reference to another module, *Stringer.netmodule*.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5e77e-122">C# コンパイラと Visual Basic コンパイラは、マルチファイル アセンブリを直接作成する場合、次の 2 種類の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-122">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>
   >
   > <span data-ttu-id="5e77e-123">2 回のコンパイルで、2 ファイルのアセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="5e77e-123">Two compilations create a two-file assembly:</span></span>
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > <span data-ttu-id="5e77e-124">1 回のコンパイルで、2 ファイルのアセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="5e77e-124">One compilation creates a two-file assembly:</span></span>
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. <span data-ttu-id="5e77e-125">[アセンブリ リンカー (Al.exe)](../tools/al-exe-assembly-linker.md) を使用して、アセンブリ マニフェストを格納する出力ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-125">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="5e77e-126">このファイルは、アセンブリの一部であるすべてのモジュールまたはリソースについての参照情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-126">This file contains reference information for all modules or resources that are part of the assembly.</span></span>

    <span data-ttu-id="5e77e-127">コマンド プロンプトに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-127">At the command prompt, type the following command:</span></span>

    <span data-ttu-id="5e77e-128">**al** \<*module name*> \<*module name*> …</span><span class="sxs-lookup"><span data-stu-id="5e77e-128">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="5e77e-129">**/main:** \<*method name*>  **/out:** \<*file name*>  **/target:** \<*assembly file type*></span><span class="sxs-lookup"><span data-stu-id="5e77e-129">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>

    <span data-ttu-id="5e77e-130">このコマンドで、*module name* 引数はアセンブリに含める各モジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-130">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="5e77e-131">**/main:** オプションは、アセンブリのエントリ ポイントであるメソッド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-131">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="5e77e-132">**/out:** オプションは、アセンブリ メタデータを格納する出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-132">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="5e77e-133">**/target:** オプションは、アセンブリがコンソール アプリケーション実行可能 ( *.exe*) ファイル、Windows 実行可能 ( *.win*) ファイル、またはライブラリ ( *.lib*) ファイルであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-133">The **/target:** option specifies that the assembly is a console application executable (*.exe*) file, a Windows executable (*.win*) file, or a library (*.lib*) file.</span></span>

    <span data-ttu-id="5e77e-134">*Al.exe* を使用して、*myAssembly.exe* というコンソール アプリケーション実行可能ファイルであるアセンブリを作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5e77e-134">In the following example, *Al.exe* creates an assembly that is a console application executable called *myAssembly.exe*.</span></span> <span data-ttu-id="5e77e-135">このアプリケーションは、*Client.netmodule* および *Stringer.netmodule* という 2 つのモジュール、および *myAssembly.exe* というアセンブリ メタデータだけを格納する実行可能ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-135">The application consists of two modules called *Client.netmodule* and *Stringer.netmodule*, and the executable file called *myAssembly.exe*, which contains only assembly metadata.</span></span> <span data-ttu-id="5e77e-136">アセンブリのエントリ ポイントは `MainClientApp` クラスの `Main` メソッドで、*Client.dll* 内に配置されています。</span><span class="sxs-lookup"><span data-stu-id="5e77e-136">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in *Client.dll*.</span></span>

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    <span data-ttu-id="5e77e-137">[MSIL 逆アセンブラー (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) を使用すると、アセンブリの内容を調査したり、ファイルがアセンブリであるかモジュールであるかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="5e77e-137">You can use the [MSIL Disassembler (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e77e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e77e-138">See also</span></span>

- [<span data-ttu-id="5e77e-139">アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="5e77e-139">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="5e77e-140">How to: View assembly contents</span><span class="sxs-lookup"><span data-stu-id="5e77e-140">How to: View assembly contents</span></span>](../../standard/assembly/view-contents.md)
- [<span data-ttu-id="5e77e-141">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="5e77e-141">How the runtime locates assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="5e77e-142">マルチファイル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5e77e-142">Multifile assemblies</span></span>](multifile-assemblies.md)

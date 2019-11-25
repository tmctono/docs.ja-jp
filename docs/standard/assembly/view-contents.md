---
title: '方法: アセンブリの内容を表示する'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 72b02209d74b6b183af6c11d9bd037889ea08543
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347054"
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="2ef48-102">方法: アセンブリの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="2ef48-102">How to: View assembly contents</span></span>

<span data-ttu-id="2ef48-103">[Ildasm.exe (IL 逆アセンブラー)](../../framework/tools/ildasm-exe-il-disassembler.md) を使用して、ファイル内の MSIL (Microsoft Intermediate Language) 情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2ef48-103">You can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="2ef48-104">調べる対象のファイルがアセンブリの場合、この情報にはアセンブリの属性と他のモジュールやアセンブリへの参照が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="2ef48-104">If the file being examined is an assembly, this information can include the assembly's attributes and references to other modules and assemblies.</span></span> <span data-ttu-id="2ef48-105">この情報は、ファイルがアセンブリまたはアセンブリの一部かどうか、およびファイルに他のモジュールまたはアセンブリへの参照があるかどうかを判断するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2ef48-105">This information can be helpful in determining whether a file is an assembly or part of an assembly and whether the file has references to other modules or assemblies.</span></span>

<span data-ttu-id="2ef48-106">*Ildasm.exe* を使用してアセンブリの内容を表示するには、コマンド プロンプトで「**ildasm \<assembly name>** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-106">To display the contents of an assembly using *Ildasm.exe*, enter **ildasm \<assembly name>** at a command prompt.</span></span> <span data-ttu-id="2ef48-107">たとえば、次のコマンドでは、*Hello.exe* アセンブリが逆アセンブルされます。</span><span class="sxs-lookup"><span data-stu-id="2ef48-107">For example, the following command disassembles the *Hello.exe* assembly.</span></span>

```cmd
ildasm Hello.exe
```

<span data-ttu-id="2ef48-108">アセンブリ マニフェスト情報を表示するには、MSIL 逆アセンブラー ウィンドウで **[マニフェスト]** アイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ef48-108">To view assembly manifest information, double-click the **Manifest** icon in the MSIL Disassembler window.</span></span>

## <a name="example"></a><span data-ttu-id="2ef48-109">例</span><span class="sxs-lookup"><span data-stu-id="2ef48-109">Example</span></span>

<span data-ttu-id="2ef48-110">次の例では、基本の "Hello World" プログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-110">The following example starts with a basic "Hello World" program.</span></span> <span data-ttu-id="2ef48-111">プログラムをコンパイルした後、*Ildasm.exe* を使用して *Hello.exe* アセンブリを逆アセンブルし、アセンブリ マニフェストを表示します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-111">After compiling the program, use *Ildasm.exe* to disassemble the *Hello.exe* assembly and view the assembly manifest.</span></span>

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

<span data-ttu-id="2ef48-112">*Hello.exe* アセンブリに対して *ildasm.exe* コマンドを実行し、MSIL 逆アセンブラー ウィンドウで **[マニフェスト]** アイコンをダブルクリックすると、次の内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="2ef48-112">Running the command *ildasm.exe* on the *Hello.exe* assembly and double-clicking the **Manifest** icon in the MSIL Disassembler window produces the following output:</span></span>

```output
// Metadata version: v4.0.30319
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 4:0:0:0
}
.assembly Hello
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module Hello.exe
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x00600000
```

<span data-ttu-id="2ef48-113">次の表では、例で使用した *Hello.exe* アセンブリのアセンブリ マニフェストにある各ディレクティブについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="2ef48-113">The following table describes each directive in the assembly manifest of the *Hello.exe* assembly used in the example:</span></span>

|<span data-ttu-id="2ef48-114">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2ef48-114">Directive</span></span>|<span data-ttu-id="2ef48-115">説明</span><span class="sxs-lookup"><span data-stu-id="2ef48-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2ef48-116">**.assembly extern \<アセンブリ名>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-116">**.assembly extern \<assembly name>**</span></span>|<span data-ttu-id="2ef48-117">現在のモジュールによって参照される項目を含む別のアセンブリを指定します (この例では `mscorlib`)。</span><span class="sxs-lookup"><span data-stu-id="2ef48-117">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|
|<span data-ttu-id="2ef48-118">**.publickeytoken \<トークン>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-118">**.publickeytoken \<token>**</span></span>|<span data-ttu-id="2ef48-119">参照されるアセンブリの実際のキーのトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-119">Specifies the token of the actual key of the referenced assembly.</span></span>|
|<span data-ttu-id="2ef48-120">**.ver \<バージョン番号>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-120">**.ver \<version number>**</span></span>|<span data-ttu-id="2ef48-121">参照されるアセンブリのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-121">Specifies the version number of the referenced assembly.</span></span>|
|<span data-ttu-id="2ef48-122">**.assembly \<アセンブリ名>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-122">**.assembly \<assembly name>**</span></span>|<span data-ttu-id="2ef48-123">アセンブリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-123">Specifies the assembly name.</span></span>|
|<span data-ttu-id="2ef48-124">**.hash algorithm \<Int32 値>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-124">**.hash algorithm \<int32 value>**</span></span>|<span data-ttu-id="2ef48-125">使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-125">Specifies the hash algorithm used.</span></span>|
|<span data-ttu-id="2ef48-126">**.ver \<バージョン番号>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-126">**.ver \<version number>**</span></span>|<span data-ttu-id="2ef48-127">アセンブリのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-127">Specifies the version number of the assembly.</span></span>|
|<span data-ttu-id="2ef48-128">**.module \<ファイル名>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-128">**.module \<file name>**</span></span>|<span data-ttu-id="2ef48-129">アセンブリを構成するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-129">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="2ef48-130">この例では、アセンブリは 1 つのファイルだけで構成されています。</span><span class="sxs-lookup"><span data-stu-id="2ef48-130">In this example, the assembly consists of only one file.</span></span>|
|<span data-ttu-id="2ef48-131">**.subsystem \<値>**</span><span class="sxs-lookup"><span data-stu-id="2ef48-131">**.subsystem \<value>**</span></span>|<span data-ttu-id="2ef48-132">プログラムに必要なアプリケーション環境を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-132">Specifies the application environment required for the program.</span></span> <span data-ttu-id="2ef48-133">この例では、値 3 は、この実行可能ファイルがコンソールで実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ef48-133">In this example, the value 3 indicates that this executable is run from a console.</span></span>|
|<span data-ttu-id="2ef48-134">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="2ef48-134">**.corflags**</span></span>|<span data-ttu-id="2ef48-135">現在メタデータ内で予約済みのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="2ef48-135">Currently a reserved field in the metadata.</span></span>|

<span data-ttu-id="2ef48-136">アセンブリ マニフェストは、アセンブリの内容に応じて、多くの異なるディレクティブを格納できます。</span><span class="sxs-lookup"><span data-stu-id="2ef48-136">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="2ef48-137">アセンブリ マニフェストに含まれる多様なディレクティブの一覧については、ECMA のドキュメント、特に「Partition II: Metadata Definition and Semantics」(パーティション II: メタデータの定義とセマンティクス) および「Partition III:CIL Instruction Set」(パーティション III: CIL 命令セット) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ef48-137">For an extensive list of the directives in the assembly manifest, see the Ecma documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set":</span></span>

- [<span data-ttu-id="2ef48-138">ECMA の C# および共通言語基盤の標準</span><span class="sxs-lookup"><span data-stu-id="2ef48-138">ECMA C# and Common Language Infrastructure standards</span></span>](/dotnet/standard/components#applicable-standards)
- [<span data-ttu-id="2ef48-139">Standard ECMA-335 - 共通言語基盤 (CLI)</span><span class="sxs-lookup"><span data-stu-id="2ef48-139">Standard ECMA-335 - Common Language Infrastructure (CLI)</span></span>](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a><span data-ttu-id="2ef48-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ef48-140">See also</span></span>

- [<span data-ttu-id="2ef48-141">アプリケーション ドメインとアセンブリ</span><span class="sxs-lookup"><span data-stu-id="2ef48-141">Application domains and assemblies</span></span>](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [<span data-ttu-id="2ef48-142">アプリケーション ドメインとアセンブリに関する方法のトピック</span><span class="sxs-lookup"><span data-stu-id="2ef48-142">Application domains and assemblies how-to topics</span></span>](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [<span data-ttu-id="2ef48-143">Ildasm.exe (IL 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="2ef48-143">Ildasm.exe (IL Disassembler)</span></span>](../../framework/tools/ildasm-exe-il-disassembler.md)

---
title: '方法: 署名のないフレンド アセンブリを作成する'
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: f8fec064507553b8208083578165965de2303a33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352436"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="92587-102">方法: 署名のないフレンド アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="92587-102">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="92587-103">この例では、署名のないアセンブリと共にフレンド アセンブリを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="92587-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="92587-104">署名のないアセンブリとフレンド アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="92587-104">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="92587-105">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="92587-105">Open a command prompt.</span></span>

2. <span data-ttu-id="92587-106">次のコードを含む、*friend_unsigned_A* という名前の C# または Visual Basic ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="92587-106">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="92587-107">コードでは <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性を使用して、フレンド アセンブリとして *friend_unsigned_B* を宣言します。</span><span class="sxs-lookup"><span data-stu-id="92587-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
   Imports System.Runtime.CompilerServices

   <Assembly: InternalsVisibleTo("friend_unsigned_B")>

   ' Friend type.
   Friend Class Class1
       Public Sub Test()
           Console.WriteLine("Class1.Test")
       End Sub
   End Class

   ' Public type with Friend member.
   Public Class Class2
       Friend Sub Test()
           Console.WriteLine("Class2.Test")
       End Sub
   End Class
   ```

3. <span data-ttu-id="92587-108">次のコマンドを使用して *friend_unsigned_A* をコンパイルして署名します。</span><span class="sxs-lookup"><span data-stu-id="92587-108">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="92587-109">次のコードを含む、*friend_unsigned_B* という名前の C# または Visual Basic ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="92587-109">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="92587-110">*friend_unsigned_A* が *friend_unsigned_B* をフレンド アセンブリとして指定しているため、*friend_unsigned_B* 内のコードは、*friend_unsigned_A* の `internal` (C#) または `Friend` (Visual Basic) 型とメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="92587-110">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

   ```vb
   ' friend_unsigned_B.vb
   ' Compile with:
   ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   Module Module1
       Sub Main()
           ' Access a Friend type.
           Dim inst1 As New Class1()
           inst1.Test()

           Dim inst2 As New Class2()
           ' Access a Friend member of a public type.
           inst2.Test()

           System.Console.ReadLine()
       End Sub
   End Module
   ```

5. <span data-ttu-id="92587-111">次のコマンドを使用して *friend_unsigned_B* をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="92587-111">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="92587-112">コンパイラによって生成されるアセンブリの名前は、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性に渡されるフレンド アセンブリ名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="92587-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="92587-113">`-out` コンパイラ オプションを使用して、出力アセンブリ ( *.exe* または *.dll*) の名前を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92587-113">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="92587-114">詳細については、「[-out (C# コンパイラ オプション)](../../csharp/language-reference/compiler-options/out-compiler-option.md)」または「[-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92587-114">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="92587-115">*friend_unsigned_B.exe* ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="92587-115">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="92587-116">このプログラムで 2 つの文字列が出力されます。**Class1.Test** と **Class2.Test**です。</span><span class="sxs-lookup"><span data-stu-id="92587-116">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="92587-117">.NET セキュリティ</span><span class="sxs-lookup"><span data-stu-id="92587-117">.NET security</span></span>

<span data-ttu-id="92587-118"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性と <xref:System.Security.Permissions.StrongNameIdentityPermission> クラスには類似点があります。</span><span class="sxs-lookup"><span data-stu-id="92587-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="92587-119">主な違いは、<xref:System.Security.Permissions.StrongNameIdentityPermission> はセキュリティ アクセス許可を要求することで特定のコード セクションを実行できますが、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性では `internal` または `Friend` (Visual Basic) 型とメンバーの参照可能範囲を制御することです。</span><span class="sxs-lookup"><span data-stu-id="92587-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="92587-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="92587-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="92587-121">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="92587-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="92587-122">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="92587-122">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="92587-123">方法: 署名されたフレンド アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="92587-123">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="92587-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="92587-124">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="92587-125">プログラミングの概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92587-125">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)

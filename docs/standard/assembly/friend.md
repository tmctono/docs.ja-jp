---
title: フレンド アセンブリ
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: a74d4b74ead8492028a092e090f9281231802a87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348178"
---
# <a name="friend-assemblies"></a><span data-ttu-id="4efbd-102">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="4efbd-102">Friend assemblies</span></span>

<span data-ttu-id="4efbd-103">"*フレンド アセンブリ*" とは、別のアセンブリの [internal](../../csharp/language-reference/keywords/internal.md) (C#) または [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) 型およびメンバーにアクセスできるアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="4efbd-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (C#) or [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) types and members.</span></span> <span data-ttu-id="4efbd-104">フレンド アセンブリとして指定した場合、public として宣言されていないその型とメンバーに、他のアセンブリからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="4efbd-105">この方法は、特に次の状況で利便性を発揮します。</span><span class="sxs-lookup"><span data-stu-id="4efbd-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="4efbd-106">単体テスト中、テスト コードが別のアセンブリで実行されている状況で、C# では `internal`、または Visual Basic では `Friend` としてマークされる、そのテスト対象のアセンブリ内のメンバーにアクセスしなければならないとき。</span><span class="sxs-lookup"><span data-stu-id="4efbd-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="4efbd-107">クラス ライブラリの開発中、そのライブラリへの追加機能が別のアセンブリにある状況で、C# では `internal`、または Visual Basic では `Friend` としてマークされる、既存アセンブリ内のメンバーにアクセスしなければならないとき。</span><span class="sxs-lookup"><span data-stu-id="4efbd-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="4efbd-108">解説</span><span class="sxs-lookup"><span data-stu-id="4efbd-108">Remarks</span></span>

<span data-ttu-id="4efbd-109"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性を利用し、特定のアセンブリの 1 つまたは複数のフレンド アセンブリを特定できます。</span><span class="sxs-lookup"><span data-stu-id="4efbd-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="4efbd-110">次の例では、*Assembly A* において <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性が使用され、フレンド アセンブリとしてアセンブリ *AssemblyB* が指定されています。</span><span class="sxs-lookup"><span data-stu-id="4efbd-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in *Assembly A* and specifies assembly *AssemblyB* as a friend assembly.</span></span> <span data-ttu-id="4efbd-111">これにより、アセンブリ *AssemblyB* では、*Assembly A* の中で `internal` (C#) または `Friend` (Visual Basic) としてマークされているすべての型とメンバーにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="4efbd-111">This gives assembly *AssemblyB* access to all types and members in *Assembly A* that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="4efbd-112">*Assembly A* のような別のアセンブリの internal 型または internal メンバーにアクセスする *AssemblyB* のようなアセンブリをコンパイルするときは、 **-out** コンパイラ オプションを使用して、出力ファイル ( *.exe* または *.dll*) の名前を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-112">When you compile an assembly like *AssemblyB* that will access internal types or internal members of another assembly like *Assembly A*, you must explicitly specify the name of the output file (*.exe* or *.dll*) by using the **-out** compiler option.</span></span> <span data-ttu-id="4efbd-113">この指定は必ず行ってください。コンパイラが外部参照にバインドする時点ではまだ、ビルド中のアセンブリの名前が生成されていないためです。</span><span class="sxs-lookup"><span data-stu-id="4efbd-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="4efbd-114">詳細については、「[-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md)」または「[-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efbd-114">For more information, see [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

```csharp
using System.Runtime.CompilerServices;
using System;

[assembly: InternalsVisibleTo("AssemblyB")]

// The class is internal by default.
class FriendClass
{
    public void Test()
    {
        Console.WriteLine("Sample Class");
    }
}

// Public class that has an internal method.
public class ClassWithFriendMethod
{
    internal void Test()
    {
        Console.WriteLine("Sample Method");
    }

}
```

```vb
Imports System.Runtime.CompilerServices
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

<span data-ttu-id="4efbd-115">`internal` (C#) または `Friend` (Visual Basic) 型およびメンバーにアクセスできるのは、明示的にフレンドとして指定されたアセンブリだけです。</span><span class="sxs-lookup"><span data-stu-id="4efbd-115">Only assemblies that you explicitly specify as friends can access `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span> <span data-ttu-id="4efbd-116">たとえば、*AssemblyB* が *Assembly A* のフレンドであり、*Assembly C* で *AssemblyB* が参照されている場合、*Assembly A* の `internal` (C#) または `Friend` (Visual Basic) 型に *Assembly C* からアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4efbd-116">For example, if *AssemblyB* is a friend of *Assembly A* and *Assembly C* references *AssemblyB*, *Assembly C* does not have access to `internal` (C#) or `Friend` (Visual Basic) types in *Assembly A*.</span></span>

<span data-ttu-id="4efbd-117">コンパイラは、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性に渡されるフレンド アセンブリ名の基本検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="4efbd-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="4efbd-118">*Assembly A* で *AssemblyB* がフレンド アセンブリとして宣言されている場合、検証規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4efbd-118">If *Assembly A* declares *AssemblyB* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="4efbd-119">*Assembly A* に厳密な名前が付けられている場合、*AssemblyB* にも厳密な名前が付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-119">If *Assembly A* is strong named, *AssemblyB* must also be strong named.</span></span> <span data-ttu-id="4efbd-120">属性に渡されるフレンド アセンブリ名は、アセンブリ名と、*AssemblyB* の署名に使用される厳密な名前のキーの公開キーで構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign *AssemblyB*.</span></span>

     <span data-ttu-id="4efbd-121">*AssemblyB* の厳密な名前を、フレンド アセンブリ名として <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性に渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4efbd-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of *AssemblyB*.</span></span> <span data-ttu-id="4efbd-122">アセンブリのバージョン、カルチャ、アーキテクチャ、公開キー トークンは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="4efbd-122">Don't include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="4efbd-123">*Assembly A* が厳密な名前でない場合、フレンド アセンブリの名前は、アセンブリ名のみで構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-123">If *Assembly A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="4efbd-124">詳細については、[署名のないフレンド アセンブリを作成する](create-unsigned-friend.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efbd-124">For more information, see [How to: Create unsigned friend assemblies](create-unsigned-friend.md).</span></span>

- <span data-ttu-id="4efbd-125">*AssemblyB* に厳密な名前が付けられている場合、プロジェクトの設定またはコマンド ラインの `/keyfile` コンパイラ オプションを使用して、*AssemblyB* に対して厳密な名前のキーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-125">If *AssemblyB* is strong named, you must specify the strong-name key for *AssemblyB* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="4efbd-126">詳細については、[署名されたフレンド アセンブリを作成する](create-signed-friend.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efbd-126">For more information, see [How to: Create signed friend assemblies](create-signed-friend.md).</span></span>

 <span data-ttu-id="4efbd-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> クラスも型を共有する機能を提供しますが、次のような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-127">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="4efbd-128">フレンド アセンブリはアセンブリ全体に適用されますが、<xref:System.Security.Permissions.StrongNameIdentityPermission> は個々の型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4efbd-128"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="4efbd-129">*AssemblyB* との間で共有したい型が *Assembly A* に数百個存在する場合、そのすべてに対して <xref:System.Security.Permissions.StrongNameIdentityPermission> を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-129">If there are hundreds of types in *Assembly A* that you want to share with *AssemblyB*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="4efbd-130">フレンド アセンブリを使用した場合、フレンド関係を 1 回宣言するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="4efbd-130">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="4efbd-131"><xref:System.Security.Permissions.StrongNameIdentityPermission> を使用する場合、共有する型をパブリックとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4efbd-131">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="4efbd-132">フレンド アセンブリを使用する場合、共有する型は `internal` (C#) または `Friend` (Visual Basic) として宣言します。</span><span class="sxs-lookup"><span data-stu-id="4efbd-132">If you use a friend assembly, the shared types are declared as `internal` (C#) or `Friend` (Visual Basic).</span></span>

<span data-ttu-id="4efbd-133">アセンブリの `internal` (C#) または `Friend` (Visual Basic) 型およびメソッドに、モジュール ファイル ( *.netmodule* 拡張子の付いたファイル) からアクセスする方法については、[-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) または [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efbd-133">For information about how to access an assembly's `internal` (C#) or `Friend` (Visual Basic) types and methods from a module file (a file with the *.netmodule* extension), see [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4efbd-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4efbd-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="4efbd-135">方法: 署名のないフレンド アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="4efbd-135">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="4efbd-136">方法: 署名されたフレンド アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="4efbd-136">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="4efbd-137">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="4efbd-137">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="4efbd-138">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4efbd-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4efbd-139">プログラミングの概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4efbd-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)

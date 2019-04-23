---
title: '方法: 署名されたフレンド アセンブリ (Visual Basic) を作成します。'
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 4ff32015647a565f7f68e944ae028deb7f738e28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324670"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="94130-102">方法: 署名されたフレンド アセンブリ (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="94130-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="94130-103">この例では、厳密な名前を持つアセンブリと共にフレンド アセンブリを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94130-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="94130-104">両方のアセンブリに厳密な名前が付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94130-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="94130-105">この例のアセンブリは両方とも同じキーを使用していますが、2 つのアセンブリそれぞれが別々のキーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="94130-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="94130-106">署名付きアセンブリとフレンド アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="94130-106">To create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="94130-107">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="94130-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="94130-108">厳密な名前ツールで次のコマンド シーケンスを使用して、キー ファイルを生成し、公開鍵を表示します。</span><span class="sxs-lookup"><span data-stu-id="94130-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="94130-109">詳細については、次を参照してください。 [Sn.exe (厳密名ツール)](../../../../framework/tools/sn-exe-strong-name-tool.md))。</span><span class="sxs-lookup"><span data-stu-id="94130-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="94130-110">この例で使用する厳密な名前キーを生成し、FriendAssemblies.snk ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="94130-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="94130-111">FriendAssemblies.snk から公開鍵を抽出し、FriendAssemblies.publickey に追加します。</span><span class="sxs-lookup"><span data-stu-id="94130-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="94130-112">FriendAssemblies.publickey ファイルに格納されている公開鍵を表示します。</span><span class="sxs-lookup"><span data-stu-id="94130-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="94130-113">という名前の Visual Basic ファイルを作成する`friend_signed_A`次のコードを格納しています。</span><span class="sxs-lookup"><span data-stu-id="94130-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="94130-114">コードでは <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性を使用して、フレンド アセンブリとして friend_signed_B を宣言します。</span><span class="sxs-lookup"><span data-stu-id="94130-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="94130-115">厳密な名前ツールは、実行するごとに新しい公開鍵を生成します。</span><span class="sxs-lookup"><span data-stu-id="94130-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="94130-116">このため、次の例に示すコード内の公開鍵を、ここで生成した公開鍵に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="94130-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4. <span data-ttu-id="94130-117">次のコマンドを使用して friend_signed_A をコンパイルして署名します。</span><span class="sxs-lookup"><span data-stu-id="94130-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5. <span data-ttu-id="94130-118">という名前の Visual Basic ファイルを作成する`friend_signed_B`次のコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94130-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="94130-119">friend_signed_A が friend_signed_B をフレンド アセンブリとして指定しているため、friend_signed_B 内のコードは、friend_signed_A の `Friend` 型とメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94130-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="94130-120">このファイルには、次のコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94130-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="94130-121">次のコマンドを使用して friend_signed_B をコンパイルして署名します。</span><span class="sxs-lookup"><span data-stu-id="94130-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="94130-122">コンパイラによって生成されたアセンブリの名前は、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性に渡されたフレンド アセンブリ名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="94130-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="94130-123">使用して、アセンブリを明示的に設定することができます、`-out`コンパイラ オプション。</span><span class="sxs-lookup"><span data-stu-id="94130-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="94130-124">詳細については、次を参照してください。 [-(Visual Basic) を](../../../../visual-basic/reference/command-line-compiler/out.md)します。</span><span class="sxs-lookup"><span data-stu-id="94130-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7. <span data-ttu-id="94130-125">friend_signed_B.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="94130-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="94130-126">プログラムには、文字列"Class1.Test"が表示されます。</span><span class="sxs-lookup"><span data-stu-id="94130-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="94130-127">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="94130-127">.NET Framework Security</span></span>  
 <span data-ttu-id="94130-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性と <xref:System.Security.Permissions.StrongNameIdentityPermission> クラスには類似点があります。</span><span class="sxs-lookup"><span data-stu-id="94130-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="94130-129">主な違いは、<xref:System.Security.Permissions.StrongNameIdentityPermission> はセキュリティ アクセス許可を要求することで特定のコード セクションを実行できますが、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性では `Friend` 型とメンバーの参照可能範囲を制御することです。</span><span class="sxs-lookup"><span data-stu-id="94130-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94130-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="94130-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="94130-131">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="94130-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="94130-132">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="94130-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="94130-133">方法: 署名のないフレンド アセンブリ (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="94130-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="94130-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="94130-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)
- <span data-ttu-id="94130-135">[Sn.exe (厳密名ツール)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="94130-135">[Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
- [<span data-ttu-id="94130-136">厳密な名前付きアセンブリの作成と使用</span><span class="sxs-lookup"><span data-stu-id="94130-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="94130-137">プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="94130-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)

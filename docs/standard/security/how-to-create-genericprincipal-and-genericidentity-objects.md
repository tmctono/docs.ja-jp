---
title: '方法: GenericPrincipal オブジェクトと GenericIdentity オブジェクトを作成する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f768242bffe619051779f87e950138ae9fcec6c
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353186"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="47248-102">方法: GenericPrincipal オブジェクトと GenericIdentity オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="47248-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

<span data-ttu-id="47248-103">@No__t-0 クラスを <xref:System.Security.Principal.GenericPrincipal> クラスと共に使用して、Windows ドメインとは無関係に存在する認証スキームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47248-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="47248-104">GenericPrincipal オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="47248-104">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="47248-105">ID クラスの新しいインスタンスを作成し、インスタンスに付ける名前で初期化します。</span><span class="sxs-lookup"><span data-stu-id="47248-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="47248-106">新しい **GenericIdentity** オブジェクトを作成し、名前 `MyUser` で初期化するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="47248-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="47248-107">**GenericPrincipal** クラスの新しいインスタンスを作成し、前に作成した **GenericIdentity** オブジェクトと、プリンシパルに関連付けるロールを表す文字列の配列で、このインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="47248-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="47248-108">管理者のロールとユーザーのロールを表す文字列の配列を指定するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="47248-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="47248-109">**GenericPrincipal** は、前の **GenericIdentity** と文字列配列で初期化されます。</span><span class="sxs-lookup"><span data-stu-id="47248-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="47248-110">次のコードを使用して、プリンシパルを現在のスレッドに結合します。</span><span class="sxs-lookup"><span data-stu-id="47248-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="47248-111">これは、プリンシパルを複数回検証する必要がある場合、アプリケーションで実行されている他のコードによって検証する必要がある場合、または @no__t 0 オブジェクトで検証する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="47248-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="47248-112">このような場合でも、プリンシパル オブジェクトをスレッドに結合せずにロール ベースの検証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="47248-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="47248-113">詳細については、「[プリンシパル オブジェクトの置き換え](../../../docs/standard/security/replacing-a-principal-object.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47248-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="47248-114">例</span><span class="sxs-lookup"><span data-stu-id="47248-114">Example</span></span>

<span data-ttu-id="47248-115">次のコード例では、**GenericPrincipal** と **GenericIdentity** のインスタンスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="47248-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="47248-116">このコードは、各オブジェクトの値をコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="47248-116">This code displays the values of these objects to the console.</span></span>

```vb
Imports System
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

    End Sub

End Class
```

```csharp
using System;
using System.Security.Principal;
using System.Threading;

public class Class1
{
    public static int Main(string[] args)
    {
    // Create generic identity.
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

<span data-ttu-id="47248-117">実行されると、アプリケーションの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="47248-117">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="47248-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="47248-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="47248-119">プリンシパル オブジェクトの置き換え</span><span class="sxs-lookup"><span data-stu-id="47248-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="47248-120">プリンシパル オブジェクトと ID オブジェクト</span><span class="sxs-lookup"><span data-stu-id="47248-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)

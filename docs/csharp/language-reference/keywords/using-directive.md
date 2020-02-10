---
title: using ディレクティブ - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 4f7ddad8c3dc12391ef6bf345a73ebb384400b38
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093150"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="f798c-102">using ディレクティブ (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f798c-102">using directive (C# Reference)</span></span>

<span data-ttu-id="f798c-103">`using` ディレクティブは、次の 3 つの用途で使用します。</span><span class="sxs-lookup"><span data-stu-id="f798c-103">The `using` directive has three uses:</span></span>

- <span data-ttu-id="f798c-104">名前空間で型の使用を許可する場合。これにより、その名前空間内では型を修飾せずに使用できます。</span><span class="sxs-lookup"><span data-stu-id="f798c-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>

    ```csharp
    using System.Text;
    ```

- <span data-ttu-id="f798c-105">アクセスを型名で修飾することなく、型の静的メンバーおよび入れ子にされた型へのアクセスを許可する場合。</span><span class="sxs-lookup"><span data-stu-id="f798c-105">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span>

    ```csharp
    using static System.Math;
    ```

    <span data-ttu-id="f798c-106">詳細については、「[using static ディレクティブ](using-static.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f798c-106">For more information, see the [using static directive](using-static.md).</span></span>

- <span data-ttu-id="f798c-107">名前空間または型のエイリアスを作成する場合。</span><span class="sxs-lookup"><span data-stu-id="f798c-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="f798c-108">これは "*using エイリアス ディレクティブ*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f798c-108">This is called a *using alias directive*.</span></span>

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

<span data-ttu-id="f798c-109">`using` キーワードは、*using ステートメント*の作成にも使用します。ファイルやフォントなどの <xref:System.IDisposable> オブジェクトを正しく処理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f798c-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="f798c-110">詳しくは、「[using ステートメント](using-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f798c-110">See [using Statement](using-statement.md) for more information.</span></span>

## <a name="using-static-type"></a><span data-ttu-id="f798c-111">using static 型</span><span class="sxs-lookup"><span data-stu-id="f798c-111">Using static type</span></span>

<span data-ttu-id="f798c-112">アクセスを型名で修飾することなく型の静的メンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f798c-112">You can access static members of a type without having to qualify the access with the type name:</span></span>

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a><span data-ttu-id="f798c-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="f798c-113">Remarks</span></span>

<span data-ttu-id="f798c-114">`using` ディレクティブのスコープは、このディレクティブが存在するファイルに限定されます。</span><span class="sxs-lookup"><span data-stu-id="f798c-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>

<span data-ttu-id="f798c-115">`using` ディレクティブは、次のように記述することができます。</span><span class="sxs-lookup"><span data-stu-id="f798c-115">The `using` directive can appear:</span></span>

- <span data-ttu-id="f798c-116">ソース コード ファイルの先頭、任意の名前空間または型定義の前。</span><span class="sxs-lookup"><span data-stu-id="f798c-116">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="f798c-117">任意の名前空間内、ただし、この名前空間内で宣言された任意の名前空間または型の前。</span><span class="sxs-lookup"><span data-stu-id="f798c-117">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="f798c-118">それ以外の場合は、コンパイラ エラー [CS1529](../../misc/cs1529.md) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f798c-118">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>

<span data-ttu-id="f798c-119">`using` 別名ディレクティブを作成すると、名前空間または型の識別子を修飾しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f798c-119">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="f798c-120">いずれの `using` ディレクティブにおいても、前に置かれる `using` に関係なく、完全に修飾された名前空間または型を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f798c-120">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="f798c-121">`using` ディレクティブの宣言内では、`using` 別名を使用することができません。</span><span class="sxs-lookup"><span data-stu-id="f798c-121">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="f798c-122">たとえば、次の場合はコンパイラ エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f798c-122">For example, the following generates a compiler error:</span></span>

```csharp
using s = System.Text;
using s.RegularExpressions; // Generates a compiler error.
```

<span data-ttu-id="f798c-123">`using` ディレクティブを作成すると、名前空間内の型を、名前空間を指定することなく使用できます。</span><span class="sxs-lookup"><span data-stu-id="f798c-123">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="f798c-124">`using` ディレクティブでは、指定した名前空間に入れ子になった別の名前空間へのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f798c-124">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>

<span data-ttu-id="f798c-125">名前空間は、ユーザー定義とシステム定義の 2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="f798c-125">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="f798c-126">ユーザー定義の名前空間は、コードで定義された名前空間です。</span><span class="sxs-lookup"><span data-stu-id="f798c-126">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="f798c-127">システム定義の名前空間の一覧については、「[.NET API ブラウザー](../../../../api/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f798c-127">For a list of the system-defined namespaces, see [.NET API Browser](../../../../api/index.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="f798c-128">例 1</span><span class="sxs-lookup"><span data-stu-id="f798c-128">Example 1</span></span>

<span data-ttu-id="f798c-129">次の例は、名前空間の `using` エイリアスを定義して使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f798c-129">The following example shows how to define and use a `using` alias for a namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

<span data-ttu-id="f798c-130">using エイリアス ディレクティブの右側には、オープン ジェネリック型を配置できません。</span><span class="sxs-lookup"><span data-stu-id="f798c-130">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="f798c-131">たとえば、`List<T>` の using エイリアスを作成することはできませんが、`List<int>` の using エイリアスは作成できます。</span><span class="sxs-lookup"><span data-stu-id="f798c-131">For example, you cannot create a using alias for a `List<T>`, but you can create one for a `List<int>`.</span></span>

## <a name="example-2"></a><span data-ttu-id="f798c-132">例 2</span><span class="sxs-lookup"><span data-stu-id="f798c-132">Example 2</span></span>

<span data-ttu-id="f798c-133">次の例は、クラスの `using` ディレクティブと `using` エイリアスを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f798c-133">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="f798c-134">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f798c-134">C# language specification</span></span>

<span data-ttu-id="f798c-135">詳細については、[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)に関するページの [using ディレクティブ](~/_csharplang/spec/namespaces.md#using-directives)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f798c-135">For more information, see [Using directives](~/_csharplang/spec/namespaces.md#using-directives) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="f798c-136">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="f798c-136">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="f798c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f798c-137">See also</span></span>

- [<span data-ttu-id="f798c-138">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f798c-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f798c-139">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f798c-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f798c-140">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="f798c-140">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="f798c-141">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="f798c-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f798c-142">名前空間</span><span class="sxs-lookup"><span data-stu-id="f798c-142">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
- [<span data-ttu-id="f798c-143">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="f798c-143">using Statement</span></span>](using-statement.md)

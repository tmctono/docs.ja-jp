---
description: using static ディレクティブ - C# リファレンス
title: using static ディレクティブ - C# リファレンス
ms.date: 03/10/2017
f1_keywords:
- using-static_CSharpKeyword
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: d117d4423a2f7c782cd6365a73e6c18298d89abc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162233"
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="baf45-103">using static ディレクティブ (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="baf45-103">using static directive (C# Reference)</span></span>

<span data-ttu-id="baf45-104">`using static` ディレクティブは、型名を指定せずにアクセスできる静的メンバーおよび入れ子にされた型を指定します。</span><span class="sxs-lookup"><span data-stu-id="baf45-104">The `using static` directive designates a type whose static members and nested types you can access without specifying a type name.</span></span> <span data-ttu-id="baf45-105">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="baf45-105">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>;
```

<span data-ttu-id="baf45-106">*fully-qualified-type-name* は、型名を指定せずに参照できる静的メンバーおよび入れ子にされた型の名前です。</span><span class="sxs-lookup"><span data-stu-id="baf45-106">where *fully-qualified-type-name* is the name of the type whose static members and nested types can be referenced without specifying a type name.</span></span> <span data-ttu-id="baf45-107">完全修飾型名 (完全な名前空間名と型名) を指定しないと、C# によってコンパイラ エラー [CS0246](../compiler-messages/cs0246.md): "型または名前空間の名前 'type/namespace' が見つかりませんでした (using ディレクティブまたはアセンブリ参照が指定されていることを確認してください)" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="baf45-107">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error [CS0246](../compiler-messages/cs0246.md): "The type or namespace name 'type/namespace' could not be found (are you missing a using directive or an assembly reference?)".</span></span>

<span data-ttu-id="baf45-108">`using static` ディレクティブは、インスタンス メンバーがある場合でも、静的メンバーがあるすべての型 (または入れ子にされた型) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="baf45-108">The `using static` directive applies to any type that has static members (or nested types), even if it also has instance members.</span></span> <span data-ttu-id="baf45-109">ただし、インスタンス メンバーは、型のインスタンスを通してのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="baf45-109">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="baf45-110">`using static` ディレクティブは、C# 6 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="baf45-110">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="baf45-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="baf45-111">Remarks</span></span>

<span data-ttu-id="baf45-112">通常は、静的メンバーを呼び出すときに、型名とメンバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="baf45-112">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="baf45-113">同じ型名を繰り返し入力してその型のメンバーを呼び出すと、コードが冗長でわかりにくくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="baf45-113">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="baf45-114">たとえば、次の `Circle` クラスの定義は、<xref:System.Math> クラスのメンバー数を参照します。</span><span class="sxs-lookup"><span data-stu-id="baf45-114">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="baf45-115">メンバーが参照されるたびに <xref:System.Math> クラスを明示的に参照する必要がなくなれば、`using static` ディレクティブによって生成されるコードがより簡潔になります。</span><span class="sxs-lookup"><span data-stu-id="baf45-115">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="baf45-116">`using static` は、指定した型で宣言されているアクセス可能な静的メンバーおよび入れ子になった型のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="baf45-116">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="baf45-117">継承されたメンバーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="baf45-117">Inherited members are not imported.</span></span>  <span data-ttu-id="baf45-118">using static ディレクティブを使用して、Visual Basic モジュールを含む、名前付きの型からインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="baf45-118">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="baf45-119">F# の最上位の関数が、有効な C# 識別子を名前に持つ名前付きの型の静的メンバーとしてメタデータに存在する場合は、その F# 関数をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="baf45-119">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>

 <span data-ttu-id="baf45-120">`using static` を使用すると、指定した型で宣言された拡張メソッドを拡張メソッドの参照で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="baf45-120">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="baf45-121">ただし、コード内で修飾なしで参照している場合は、拡張メソッドの名前はスコープにインポートされません。</span><span class="sxs-lookup"><span data-stu-id="baf45-121">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>

 <span data-ttu-id="baf45-122">同じコンパイル単位または名前空間の多様な `using static` ディレクティブによってさまざまな型からインポートされた同じ名前を持つメソッドが、メソッド グループを形成します。</span><span class="sxs-lookup"><span data-stu-id="baf45-122">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="baf45-123">これらのメソッド グループ内のオーバーロードの解決方法は、C# の通常の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="baf45-123">Overload resolution within these method groups follows normal C# rules.</span></span>

## <a name="example"></a><span data-ttu-id="baf45-124">例</span><span class="sxs-lookup"><span data-stu-id="baf45-124">Example</span></span>

<span data-ttu-id="baf45-125">次の例では、`using static` ディレクティブを使用して、<xref:System.Console> クラス、<xref:System.Math> クラス、および <xref:System.String> クラスの静的メンバーを、型名を指定せずに使用できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="baf45-125">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="baf45-126">上の例では、`using static` ディレクティブを <xref:System.Double> 型に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="baf45-126">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="baf45-127">それにより、型名を指定せずに、<xref:System.Double.TryParse(System.String,System.Double@)> メソッドを呼び出せるようになります。</span><span class="sxs-lookup"><span data-stu-id="baf45-127">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="baf45-128">ただし、どの数値型の `TryParse` メソッドが呼び出されたかを判断するために `using static` ディレクティブを確認する必要が出てくるため、コードが読みにくくなります。</span><span class="sxs-lookup"><span data-stu-id="baf45-128">However, this creates less readable code, since it becomes necessary to check the `using static` directives to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="baf45-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="baf45-129">See also</span></span>

- [<span data-ttu-id="baf45-130">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="baf45-130">using directive</span></span>](using-directive.md)
- [<span data-ttu-id="baf45-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="baf45-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="baf45-132">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="baf45-132">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="baf45-133">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="baf45-133">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="baf45-134">名前空間</span><span class="sxs-lookup"><span data-stu-id="baf45-134">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

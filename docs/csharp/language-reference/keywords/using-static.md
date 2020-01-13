---
title: using static ディレクティブ - C# リファレンス
ms.date: 03/10/2017
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: 55847aceb9fdf032ba533b82ee59be53761fa2c2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712950"
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="60243-102">using static ディレクティブ (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="60243-102">using static directive (C# Reference)</span></span>

<span data-ttu-id="60243-103">`using static` ディレクティブは、型名を指定せずにアクセスできる静的メンバーおよび入れ子にされた型を指定します。</span><span class="sxs-lookup"><span data-stu-id="60243-103">The `using static` directive designates a type whose static members and nested types you can access without specifying a type name.</span></span> <span data-ttu-id="60243-104">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60243-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>;
```

<span data-ttu-id="60243-105">*fully-qualified-type-name* は、型名を指定せずに参照できる静的メンバーおよび入れ子にされた型の名前です。</span><span class="sxs-lookup"><span data-stu-id="60243-105">where *fully-qualified-type-name* is the name of the type whose static members and nested types can be referenced without specifying a type name.</span></span> <span data-ttu-id="60243-106">完全修飾型名 (完全な名前空間名と型名) を指定しないと、C# によってコンパイラ エラー [CS0246](../compiler-messages/cs0246.md): "型または名前空間の名前 'type/namespace' が見つかりませんでした (using ディレクティブまたはアセンブリ参照が指定されていることを確認してください)" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="60243-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error [CS0246](../compiler-messages/cs0246.md): "The type or namespace name 'type/namespace' could not be found (are you missing a using directive or an assembly reference?)".</span></span>

<span data-ttu-id="60243-107">`using static` ディレクティブは、インスタンス メンバーがある場合でも、静的メンバーがあるすべての型 (または入れ子にされた型) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="60243-107">The `using static` directive applies to any type that has static members (or nested types), even if it also has instance members.</span></span> <span data-ttu-id="60243-108">ただし、インスタンス メンバーは、型のインスタンスを通してのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="60243-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="60243-109">`using static` ディレクティブは、C# 6 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="60243-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="60243-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="60243-110">Remarks</span></span>

<span data-ttu-id="60243-111">通常は、静的メンバーを呼び出すときに、型名とメンバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="60243-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="60243-112">同じ型名を繰り返し入力してその型のメンバーを呼び出すと、コードが冗長でわかりにくくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60243-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="60243-113">たとえば、次の `Circle` クラスの定義は、<xref:System.Math> クラスのメンバー数を参照します。</span><span class="sxs-lookup"><span data-stu-id="60243-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="60243-114">メンバーが参照されるたびに <xref:System.Math> クラスを明示的に参照する必要がなくなれば、`using static` ディレクティブによって生成されるコードがより簡潔になります。</span><span class="sxs-lookup"><span data-stu-id="60243-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="60243-115">`using static` は、指定した型で宣言されているアクセス可能な静的メンバーおよび入れ子になった型のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="60243-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="60243-116">継承されたメンバーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="60243-116">Inherited members are not imported.</span></span>  <span data-ttu-id="60243-117">using static ディレクティブを使用して、Visual Basic モジュールを含む、名前付きの型からインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="60243-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="60243-118">F# の最上位の関数が、有効な C# 識別子を名前に持つ名前付きの型の静的メンバーとしてメタデータに存在する場合は、その F# 関数をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="60243-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>

 <span data-ttu-id="60243-119">`using static` を使用すると、指定した型で宣言された拡張メソッドを拡張メソッドの参照で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="60243-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="60243-120">ただし、コード内で修飾なしで参照している場合は、拡張メソッドの名前はスコープにインポートされません。</span><span class="sxs-lookup"><span data-stu-id="60243-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>

 <span data-ttu-id="60243-121">同じコンパイル単位または名前空間の多様な `using static` ディレクティブによってさまざまな型からインポートされた同じ名前を持つメソッドが、メソッド グループを形成します。</span><span class="sxs-lookup"><span data-stu-id="60243-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="60243-122">これらのメソッド グループ内のオーバーロードの解決方法は、C# の通常の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="60243-122">Overload resolution within these method groups follows normal C# rules.</span></span>

## <a name="example"></a><span data-ttu-id="60243-123">例</span><span class="sxs-lookup"><span data-stu-id="60243-123">Example</span></span>

<span data-ttu-id="60243-124">次の例では、`using static` ディレクティブを使用して、<xref:System.Console> クラス、<xref:System.Math> クラス、および <xref:System.String> クラスの静的メンバーを、型名を指定せずに使用できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="60243-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="60243-125">上の例では、`using static` ディレクティブを <xref:System.Double> 型に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="60243-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="60243-126">それにより、型名を指定せずに、<xref:System.Double.TryParse(System.String,System.Double@)> メソッドを呼び出せるようになります。</span><span class="sxs-lookup"><span data-stu-id="60243-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="60243-127">ただし、どの数値型の `TryParse` メソッドが呼び出されたかを判断するために `using static` ステートメントを確認する必要が出てくるため、コードが読みにくくなります。</span><span class="sxs-lookup"><span data-stu-id="60243-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="60243-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="60243-128">See also</span></span>

- [<span data-ttu-id="60243-129">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="60243-129">using directive</span></span>](using-directive.md)
- [<span data-ttu-id="60243-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="60243-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="60243-131">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="60243-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="60243-132">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="60243-132">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="60243-133">名前空間</span><span class="sxs-lookup"><span data-stu-id="60243-133">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

---
title: typeof - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 7962a3d0a5885e64701cb9d9a4d689cd982b9830
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422554"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="7975c-102">typeof (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7975c-102">typeof (C# Reference)</span></span>

<span data-ttu-id="7975c-103">型の <xref:System.Type?displayProperty=nameWithType> オブジェクトを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7975c-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="7975c-104">`typeof` 式は次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="7975c-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="7975c-105">コメント</span><span class="sxs-lookup"><span data-stu-id="7975c-105">Remarks</span></span>

<span data-ttu-id="7975c-106">式の実行時の型を取得する場合は、次の例のように、.NET Framework のメソッド <xref:System.Object.GetType%2A> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7975c-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="7975c-107">`typeof` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="7975c-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="7975c-108">`typeof` 演算子は、オープン ジェネリック型に対しても使用できます。</span><span class="sxs-lookup"><span data-stu-id="7975c-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="7975c-109">複数の型パラメーターを持つ型には、適切な数のコンマを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7975c-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="7975c-110">たとえば、<xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> には 2 つの型引数があるため、1 つのコンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="7975c-110">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> has two type arguments, so you use one comma:</span></span>

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

<span data-ttu-id="7975c-111">次の例は、メソッドの戻り値の型がジェネリック <xref:System.Collections.Generic.IEnumerable%601> であるかどうかを確認する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7975c-111">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="7975c-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> では、戻り値の型が <xref:System.Collections.Generic.IEnumerable%601> でない場合、`null` ジェネリック型が返されます。</span><span class="sxs-lookup"><span data-stu-id="7975c-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="7975c-113">例</span><span class="sxs-lookup"><span data-stu-id="7975c-113">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="7975c-114">例</span><span class="sxs-lookup"><span data-stu-id="7975c-114">Example</span></span>

<span data-ttu-id="7975c-115">このサンプルでは、<xref:System.Object.GetType%2A> メソッドを使用して、数値計算結果の格納に使用される型を確認しています。</span><span class="sxs-lookup"><span data-stu-id="7975c-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="7975c-116">これは、結果の数のストレージ要件によって変わります。</span><span class="sxs-lookup"><span data-stu-id="7975c-116">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="7975c-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="7975c-117">C# language specification</span></span>

<span data-ttu-id="7975c-118">詳細については、「[C# 言語仕様](../language-specification/index.md)」の [typeof 演算子](~/_csharplang/spec/expressions.md#the-typeof-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7975c-118">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="7975c-119">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="7975c-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="7975c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7975c-120">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="7975c-121">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7975c-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="7975c-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7975c-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7975c-123">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="7975c-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="7975c-124">is</span><span class="sxs-lookup"><span data-stu-id="7975c-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)

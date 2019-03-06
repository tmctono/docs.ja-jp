---
title: . 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836462"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="93f9a-103">.</span><span class="sxs-lookup"><span data-stu-id="93f9a-103">.</span></span> <span data-ttu-id="93f9a-104">演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="93f9a-104">operator (C# Reference)</span></span>

<span data-ttu-id="93f9a-105">ドット (`.`) は、通常、メンバー アクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="93f9a-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="93f9a-106">以下の例に示すように、名前空間のメンバーまたは型にアクセスするために `.` トークンを使います。</span><span class="sxs-lookup"><span data-stu-id="93f9a-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="93f9a-107">次の [`using` ディレクティブ](../keywords/using-directive.md)の例に示すように、`.` を使って、名前空間内の入れ子になった名前空間にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="93f9a-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="93f9a-108">次のコードに示すように、`.` を使って "*修飾名*" を作成して名前空間内の型にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="93f9a-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="93f9a-109">[`using` ディレクティブ](../keywords/using-directive.md)を使い、必要に応じて修飾名を利用します。</span><span class="sxs-lookup"><span data-stu-id="93f9a-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="93f9a-110">次のコードに示すように、`.` を使って、[型のメンバー](../../programming-guide/classes-and-structs/index.md#members) (静的および非静的) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="93f9a-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="93f9a-111">また、`.` を使って[拡張メソッド](../../programming-guide/classes-and-structs/extension-methods.md)を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="93f9a-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="93f9a-112">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="93f9a-112">Operator overloadability</span></span>

<span data-ttu-id="93f9a-113">`.` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="93f9a-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="93f9a-114">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="93f9a-114">C# language specification</span></span>

<span data-ttu-id="93f9a-115">詳細については、[C# 言語仕様](../language-specification/index.md)に関するページの「[Member access (メンバー アクセス)](~/_csharplang/spec/expressions.md#member-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93f9a-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93f9a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="93f9a-116">See also</span></span>

- [<span data-ttu-id="93f9a-117">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="93f9a-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="93f9a-118">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="93f9a-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="93f9a-119">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="93f9a-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="93f9a-120">[?. および ?[] 演算子](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="93f9a-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>
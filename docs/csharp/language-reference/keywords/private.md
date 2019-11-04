---
title: private キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 19e2925cd65cc9c68ff50d370398a4f401275940
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422588"
---
# <a name="private-c-reference"></a><span data-ttu-id="b5ce7-102">private (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b5ce7-102">private (C# Reference)</span></span>

<span data-ttu-id="b5ce7-103">`private` キーワードはメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-103">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="b5ce7-104">このページでは、`private` アクセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-104">This page covers `private` access.</span></span> <span data-ttu-id="b5ce7-105">`private` キーワードも [`private protected`](./private-protected.md) アクセス修飾子に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="b5ce7-106">プライベート アクセスは、最も制限の多いアクセス レベルです。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="b5ce7-107">次の例に示すように、プライベート メンバーは、宣言されているクラスまたは構造体の本体内でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="b5ce7-108">同じ本体にある入れ子にされた型も、プライベート メンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-108">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="b5ce7-109">プライベート メンバーへの参照を、クラスの外側やメンバーが宣言されているクラスの外側から行った場合は、コンパイル時のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="b5ce7-110">`private` とその他のアクセス修飾子の比較については、「[アクセシビリティ レベル](accessibility-levels.md)」と「[アクセス修飾子](../../programming-guide/classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="b5ce7-111">例</span><span class="sxs-lookup"><span data-stu-id="b5ce7-111">Example</span></span>

<span data-ttu-id="b5ce7-112">この例では、`Employee` クラスに `name` と `salary` という 2 つのプライベート データ メンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="b5ce7-113">これらのメンバーは、プライベート メンバーであり、メンバー メソッド以外からはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="b5ce7-114">`GetName` と `Salary` というパブリック メソッドが追加されており、プライベート メンバーへの制御されたアクセスが許可されています。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="b5ce7-115">`name` メンバーはパブリック メソッドを通してアクセスされ、`salary` メンバーはパブリックな読み取り専用プロパティを通してアクセスされます</span><span class="sxs-lookup"><span data-stu-id="b5ce7-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="b5ce7-116">(詳細については、「[プロパティ](../../programming-guide/classes-and-structs/properties.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-116">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="b5ce7-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b5ce7-117">C# language specification</span></span>  

<span data-ttu-id="b5ce7-118">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[宣言されたアクセシビリティ](~/_csharplang/spec/basic-concepts.md#declared-accessibility)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b5ce7-119">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="b5ce7-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ce7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5ce7-120">See also</span></span>

- [<span data-ttu-id="b5ce7-121">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b5ce7-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b5ce7-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b5ce7-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b5ce7-123">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b5ce7-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b5ce7-124">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="b5ce7-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="b5ce7-125">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="b5ce7-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="b5ce7-126">修飾子</span><span class="sxs-lookup"><span data-stu-id="b5ce7-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b5ce7-127">public</span><span class="sxs-lookup"><span data-stu-id="b5ce7-127">public</span></span>](public.md)
- [<span data-ttu-id="b5ce7-128">protected</span><span class="sxs-lookup"><span data-stu-id="b5ce7-128">protected</span></span>](protected.md)
- [<span data-ttu-id="b5ce7-129">internal</span><span class="sxs-lookup"><span data-stu-id="b5ce7-129">internal</span></span>](internal.md)

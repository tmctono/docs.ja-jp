---
description: private キーワード - C# リファレンス
title: private キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: e6f40712fd2cca6d7b1f64760f1c6c5dd5c71370
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139399"
---
# <a name="private-c-reference"></a><span data-ttu-id="b507d-103">private (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b507d-103">private (C# Reference)</span></span>

<span data-ttu-id="b507d-104">`private` キーワードはメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="b507d-104">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="b507d-105">このページでは、`private` アクセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b507d-105">This page covers `private` access.</span></span> <span data-ttu-id="b507d-106">`private` キーワードも [`private protected`](./private-protected.md) アクセス修飾子に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b507d-106">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="b507d-107">プライベート アクセスは、最も制限の多いアクセス レベルです。</span><span class="sxs-lookup"><span data-stu-id="b507d-107">Private access is the least permissive access level.</span></span> <span data-ttu-id="b507d-108">次の例に示すように、プライベート メンバーは、宣言されているクラスまたは構造体の本体内でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b507d-108">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="b507d-109">同じ本体にある入れ子にされた型も、プライベート メンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b507d-109">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="b507d-110">プライベート メンバーへの参照を、クラスの外側やメンバーが宣言されているクラスの外側から行った場合は、コンパイル時のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b507d-110">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="b507d-111">`private` とその他のアクセス修飾子の比較については、「[アクセシビリティ レベル](accessibility-levels.md)」と「[アクセス修飾子](../../programming-guide/classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b507d-111">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="b507d-112">例</span><span class="sxs-lookup"><span data-stu-id="b507d-112">Example</span></span>

<span data-ttu-id="b507d-113">この例では、`Employee` クラスに `name` と `salary` という 2 つのプライベート データ メンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b507d-113">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="b507d-114">これらのメンバーは、プライベート メンバーであり、メンバー メソッド以外からはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b507d-114">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="b507d-115">`GetName` と `Salary` というパブリック メソッドが追加されており、プライベート メンバーへの制御されたアクセスが許可されています。</span><span class="sxs-lookup"><span data-stu-id="b507d-115">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="b507d-116">`name` メンバーはパブリック メソッドを通してアクセスされ、`salary` メンバーはパブリックな読み取り専用プロパティを通してアクセスされます</span><span class="sxs-lookup"><span data-stu-id="b507d-116">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="b507d-117">(詳細については、「[プロパティ](../../programming-guide/classes-and-structs/properties.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b507d-117">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="b507d-118">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b507d-118">C# language specification</span></span>  

<span data-ttu-id="b507d-119">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[宣言されたアクセシビリティ](~/_csharplang/spec/basic-concepts.md#declared-accessibility)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b507d-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b507d-120">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="b507d-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b507d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b507d-121">See also</span></span>

- [<span data-ttu-id="b507d-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b507d-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b507d-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b507d-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b507d-124">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b507d-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b507d-125">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="b507d-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="b507d-126">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="b507d-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="b507d-127">修飾子</span><span class="sxs-lookup"><span data-stu-id="b507d-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b507d-128">public</span><span class="sxs-lookup"><span data-stu-id="b507d-128">public</span></span>](public.md)
- [<span data-ttu-id="b507d-129">protected</span><span class="sxs-lookup"><span data-stu-id="b507d-129">protected</span></span>](protected.md)
- [<span data-ttu-id="b507d-130">internal</span><span class="sxs-lookup"><span data-stu-id="b507d-130">internal</span></span>](internal.md)

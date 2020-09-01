---
description: public キーワード - C# リファレンス
title: public キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 26edaf7538d11d082a4b8863228213c3ebc46937
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122343"
---
# <a name="public-c-reference"></a><span data-ttu-id="3de06-103">public (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3de06-103">public (C# Reference)</span></span>

<span data-ttu-id="3de06-104">`public` キーワードは、型と型のメンバーを示すアクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="3de06-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="3de06-105">パブリック アクセスは、最も制限の少ないアクセス レベルです。</span><span class="sxs-lookup"><span data-stu-id="3de06-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="3de06-106">次の例のように、パブリック メンバーへのアクセスには制限がありません。</span><span class="sxs-lookup"><span data-stu-id="3de06-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="3de06-107">詳しくは、「[アクセス修飾子](../../programming-guide/classes-and-structs/access-modifiers.md)」および「[アクセシビリティ レベル](accessibility-levels.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3de06-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="3de06-108">例</span><span class="sxs-lookup"><span data-stu-id="3de06-108">Example</span></span>

<span data-ttu-id="3de06-109">次の例では、2 つのクラス (`PointTest` と `MainClass`) が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="3de06-109">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="3de06-110">`PointTest` のパブリック メンバー `x` および `y` は、`MainClass` から直接アクセスされます。</span><span class="sxs-lookup"><span data-stu-id="3de06-110">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="3de06-111">`public` アクセス レベルを [private](private.md) または [protected](protected.md) に変更すると、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3de06-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="3de06-112">'PointTest.y' はアクセスできない保護レベルになっています。</span><span class="sxs-lookup"><span data-stu-id="3de06-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3de06-113">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="3de06-113">C# language specification</span></span>  

<span data-ttu-id="3de06-114">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[宣言されたアクセシビリティ](~/_csharplang/spec/basic-concepts.md#declared-accessibility)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3de06-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="3de06-115">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="3de06-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="3de06-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3de06-116">See also</span></span>

- [<span data-ttu-id="3de06-117">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3de06-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3de06-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3de06-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3de06-119">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="3de06-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="3de06-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="3de06-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3de06-121">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="3de06-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="3de06-122">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="3de06-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="3de06-123">修飾子</span><span class="sxs-lookup"><span data-stu-id="3de06-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="3de06-124">private</span><span class="sxs-lookup"><span data-stu-id="3de06-124">private</span></span>](private.md)
- [<span data-ttu-id="3de06-125">protected</span><span class="sxs-lookup"><span data-stu-id="3de06-125">protected</span></span>](protected.md)
- [<span data-ttu-id="3de06-126">internal</span><span class="sxs-lookup"><span data-stu-id="3de06-126">internal</span></span>](internal.md)

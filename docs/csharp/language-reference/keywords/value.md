---
title: value コンテキスト キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 84d0c51ddafb59144f4ba8c6e73412642fa8fa28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712898"
---
# <a name="value-c-reference"></a><span data-ttu-id="aa9cc-102">value (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="aa9cc-102">value (C# Reference)</span></span>

<span data-ttu-id="aa9cc-103">コンテキスト キーワード `value` は、`set` アクセサーの [property](../../programming-guide/classes-and-structs/properties.md) と [indexer](../../programming-guide/indexers/index.md) 宣言で使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-103">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="aa9cc-104">これは、メソッドの入力パラメーターに似ています。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-104">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="aa9cc-105">`value` という単語は、クライアント コードでプロパティまたはインデクサーに割り当てる値を表します。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-105">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="aa9cc-106">次の例の `MyDerivedClass` には、`Name` というプロパティがあります。このプロパティは `value` パラメーターを使用して、バッキング フィールド `name` に新しい文字列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="aa9cc-107">クライアント コードから見ると、演算は簡単な代入演算として記述されます。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="aa9cc-108">詳細については、[プロパティ](../../programming-guide/classes-and-structs/properties.md)と[インデクサー](../../programming-guide/indexers/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-108">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="aa9cc-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="aa9cc-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="aa9cc-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa9cc-110">See also</span></span>

- [<span data-ttu-id="aa9cc-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="aa9cc-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="aa9cc-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="aa9cc-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="aa9cc-113">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="aa9cc-113">C# Keywords</span></span>](index.md)

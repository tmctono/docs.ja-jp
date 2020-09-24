---
description: value コンテキスト キーワード - C# リファレンス
title: value コンテキスト キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828917"
---
# <a name="value-c-reference"></a><span data-ttu-id="7ee70-103">value (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7ee70-103">value (C# Reference)</span></span>

<span data-ttu-id="7ee70-104">コンテキスト キーワード `value` は、`set` アクセサーの [property](../../programming-guide/classes-and-structs/properties.md) と [indexer](../../programming-guide/indexers/index.md) 宣言で使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ee70-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="7ee70-105">これは、メソッドの入力パラメーターに似ています。</span><span class="sxs-lookup"><span data-stu-id="7ee70-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="7ee70-106">`value` という単語は、クライアント コードでプロパティまたはインデクサーに割り当てる値を表します。</span><span class="sxs-lookup"><span data-stu-id="7ee70-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="7ee70-107">次の例の `MyDerivedClass` には、`Name` というプロパティがあります。このプロパティは `value` パラメーターを使用して、バッキング フィールド `name` に新しい文字列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7ee70-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="7ee70-108">クライアント コードから見ると、演算は簡単な代入演算として記述されます。</span><span class="sxs-lookup"><span data-stu-id="7ee70-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="7ee70-109">詳細については、[プロパティ](../../programming-guide/classes-and-structs/properties.md)と[インデクサー](../../programming-guide/indexers/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ee70-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexers](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7ee70-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="7ee70-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7ee70-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ee70-111">See also</span></span>

- [<span data-ttu-id="7ee70-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7ee70-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7ee70-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7ee70-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7ee70-114">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="7ee70-114">C# Keywords</span></span>](index.md)

---
description: set キーワード - C# リファレンス
title: set キーワード - C# リファレンス
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: ff0c99e5d4d6271351783befd6650d9a77f39886
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136916"
---
# <a name="set-c-reference"></a><span data-ttu-id="f32b4-103">set (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f32b4-103">set (C# Reference)</span></span>

<span data-ttu-id="f32b4-104">`set` キーワードは、プロパティまたはインデクサーで、プロパティ値またはインデクサーの要素値を割り当てる "*アクセサー*" メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="f32b4-104">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="f32b4-105">使用例を含む詳細については、「[プロパティ](../../programming-guide/classes-and-structs/properties.md)」、「[自動実装プロパティ](../../programming-guide/classes-and-structs/auto-implemented-properties.md)」、および「[インデクサー](../../programming-guide/indexers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f32b4-105">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="f32b4-106">次の例では、`Seconds` という名前のプロパティの `get` アクセサーと `set` アクセサーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f32b4-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="f32b4-107">また、`_seconds` という名前のプライベート フィールドを使って、プロパティの値を戻しています。</span><span class="sxs-lookup"><span data-stu-id="f32b4-107">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

<span data-ttu-id="f32b4-108">多くの場合、前の例のように、`set` アクセサーは値を割り当てる 1 つのステートメントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f32b4-108">Often, the `set` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="f32b4-109">C# 7.0 以降では、式形式のメンバーとして `set` アクセサーを実装できます。</span><span class="sxs-lookup"><span data-stu-id="f32b4-109">Starting with C# 7.0, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="f32b4-110">次の例では、`get` アクセサーと `set` アクセサーの両方を、式形式のメンバーとして実装しています。</span><span class="sxs-lookup"><span data-stu-id="f32b4-110">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
<span data-ttu-id="f32b4-111">プロパティの `get` アクセサーと `set` アクセサーがプライベート バッキング フィールドの値の設定と取得以外の操作を実行しない単純な場合では、自動実装プロパティに対する C# コンパイラのサポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f32b4-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="f32b4-112">次の例では、自動実装プロパティとして `Hours` を実装しています。</span><span class="sxs-lookup"><span data-stu-id="f32b4-112">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="f32b4-113">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f32b4-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f32b4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f32b4-114">See also</span></span>

- [<span data-ttu-id="f32b4-115">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f32b4-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f32b4-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f32b4-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f32b4-117">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="f32b4-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f32b4-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f32b4-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

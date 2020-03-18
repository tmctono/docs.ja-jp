---
title: get - C# リファレンス
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: 61d8c02aaf13f43ff8ea17c1e868ea9fd52893c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173628"
---
# <a name="get-c-reference"></a><span data-ttu-id="11b95-102">get (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="11b95-102">get (C# Reference)</span></span>

<span data-ttu-id="11b95-103">`get` キーワードは、プロパティの*アクセサー*メソッド、またはプロパティ値かインデクサー要素を返すインデクサーを定義します。</span><span class="sxs-lookup"><span data-stu-id="11b95-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="11b95-104">詳しくは、「[プロパティ (C# プログラミング ガイド)](../../programming-guide/classes-and-structs/properties.md)」、「[自動実装するプロパティ (C# プログラミング ガイド)](../../programming-guide/classes-and-structs/auto-implemented-properties.md)」、および「[インデクサー (C# プログラミング ガイド)](../../programming-guide/indexers/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11b95-104">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="11b95-105">次の例では、`get` という名前のプロパティの `set` アクセサーと `Seconds` アクセサーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="11b95-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="11b95-106">また、`_seconds` という名前のプライベート フィールドを使って、プロパティの値を戻しています。</span><span class="sxs-lookup"><span data-stu-id="11b95-106">It uses a private field named `_seconds` to back the property value.</span></span>  

 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="11b95-107">多くの場合、前の例のように、`get` アクセサーは値を返す 1 つのステートメントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="11b95-107">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="11b95-108">C# 7.0 以降では、式形式のメンバーとして `get` アクセサーを実装できます。</span><span class="sxs-lookup"><span data-stu-id="11b95-108">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="11b95-109">次の例では、`get` アクセサーと `set` アクセサーの両方を、式形式のメンバーとして実装しています。</span><span class="sxs-lookup"><span data-stu-id="11b95-109">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]

<span data-ttu-id="11b95-110">プロパティの `get` アクセサーと `set` アクセサーがプライベート バッキング フィールドの値の設定と取得以外の操作を実行しない単純な場合では、自動実装プロパティに対する C# コンパイラのサポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="11b95-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="11b95-111">次の例では、自動実装プロパティとして `Hours` を実装しています。</span><span class="sxs-lookup"><span data-stu-id="11b95-111">The following example implements `Hours` as an auto-implemented property.</span></span>
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="11b95-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="11b95-112">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11b95-113">参照</span><span class="sxs-lookup"><span data-stu-id="11b95-113">See also</span></span>

- [<span data-ttu-id="11b95-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="11b95-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="11b95-115">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="11b95-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="11b95-116">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="11b95-116">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="11b95-117">Properties</span><span class="sxs-lookup"><span data-stu-id="11b95-117">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

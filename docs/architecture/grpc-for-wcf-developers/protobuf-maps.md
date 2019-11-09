---
title: Protobuf maps for dictionary-gRPC for WCF 開発者
description: Protobuf maps を使用してを表す方法について説明します。NET の辞書型。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: aef6b0f378e7a63f362ec42642cae15b32d49a08
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841451"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="7efc9-103">Protobuf のディクショナリのマップ</span><span class="sxs-lookup"><span data-stu-id="7efc9-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="7efc9-104">メッセージ内の名前付きの値の任意のコレクションを表すことができることが重要です。</span><span class="sxs-lookup"><span data-stu-id="7efc9-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="7efc9-105">.NET では、通常、ディクショナリ型を使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="7efc9-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="7efc9-106">Protobuf は、.NET <xref:System.Collections.Generic.IDictionary%602> 型に相当 `map<key_type, value_type>` 型です。</span><span class="sxs-lookup"><span data-stu-id="7efc9-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="7efc9-107">このセクションでは、Protobuf で `map` を宣言する方法と、生成されたコードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7efc9-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="7efc9-108">生成されたコードでは、`map` フィールドは、<xref:System.Collections.Generic.IDictionary%602>を含む標準の .NET コレクションインターフェイスを実装する `Google.Protobuf.Collections.MapField<TKey, TValue>` クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7efc9-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="7efc9-109">マップフィールドは、メッセージ定義内で直接繰り返すことはできませんが、次の例のように、マップを含む入れ子になったメッセージを作成し、メッセージの種類で `repeated` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7efc9-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="7efc9-110">コードでの MapField プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="7efc9-110">Using MapField properties in code</span></span>

<span data-ttu-id="7efc9-111">`map` フィールドから生成された `MapField` プロパティは読み取り専用であり、`null`されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7efc9-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="7efc9-112">マッププロパティを設定するには、空の `MapField` プロパティの `Add(IDictionary<TKey,TValue> values)` メソッドを使用して、任意の .NET ディクショナリから値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="7efc9-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="7efc9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7efc9-113">Further reading</span></span>

<span data-ttu-id="7efc9-114">Protobuf の詳細については、公式の[Protobuf のドキュメント](https://developers.google.com/protocol-buffers/docs/overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7efc9-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7efc9-115">[前へ](protobuf-enums.md)
>[次へ](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="7efc9-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>

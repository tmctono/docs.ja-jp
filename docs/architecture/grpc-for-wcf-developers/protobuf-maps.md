---
title: Protobuf maps for dictionary-gRPC for WCF 開発者
description: Protobuf maps を使用して .NET で辞書型を表す方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543132"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="d6620-103">Protobuf のディクショナリのマップ</span><span class="sxs-lookup"><span data-stu-id="d6620-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="d6620-104">メッセージ内の名前付きの値の任意のコレクションを表すことができることが重要です。</span><span class="sxs-lookup"><span data-stu-id="d6620-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="d6620-105">.NET では、通常、これはディクショナリ型によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d6620-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="d6620-106">プロトコルバッファー (Protobuf) の .NET <xref:System.Collections.Generic.IDictionary%602> 型に相当するものは、`map<key_type, value_type>` の種類です。</span><span class="sxs-lookup"><span data-stu-id="d6620-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="d6620-107">このセクションでは、Protobuf で `map` 型を宣言する方法と、生成されたコードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6620-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="d6620-108">生成されたコードでは、`map` フィールドは `Google.Protobuf.Collections.MapField<TKey, TValue>` クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6620-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="d6620-109">このクラスは、<xref:System.Collections.Generic.IDictionary%602>を含む標準の .NET コレクションインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d6620-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="d6620-110">マップフィールドは、メッセージ定義内で直接繰り返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d6620-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="d6620-111">ただし、次の例のように、マップを含む入れ子になったメッセージを作成し、メッセージの種類に `repeated` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d6620-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="d6620-112">コードでの MapField プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="d6620-112">Using MapField properties in code</span></span>

<span data-ttu-id="d6620-113">`map` フィールドから生成された `MapField` プロパティは読み取り専用であり、`null`されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d6620-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="d6620-114">マッププロパティを設定するには、空の `MapField` プロパティの `Add(IDictionary<TKey,TValue> values)` メソッドを使用して、任意の .NET ディクショナリから値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d6620-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="d6620-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6620-115">Further reading</span></span>

<span data-ttu-id="d6620-116">Protobuf の詳細については、公式の[Protobuf のドキュメント](https://developers.google.com/protocol-buffers/docs/overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6620-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d6620-117">[前へ](protobuf-enums.md)
>[次へ](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="d6620-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>

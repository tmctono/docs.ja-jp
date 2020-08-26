---
title: リストと配列の繰り返しフィールド-WCF 開発者向けの gRPC
description: Protobuf がコレクションを処理する方法と、それらが .NET コレクションにどのように関連しているかを理解します。
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867504"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="2ef03-103">リストと配列の繰り返しフィールド</span><span class="sxs-lookup"><span data-stu-id="2ef03-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="2ef03-104">プレフィックスキーワードを使用して、プロトコルバッファー (Protobuf) でリストを指定し `repeated` ます。</span><span class="sxs-lookup"><span data-stu-id="2ef03-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="2ef03-105">次の例は、リストを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2ef03-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="2ef03-106">生成されたコードでは、 `repeated` フィールドは、 [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] 組み込みの .net コレクション型ではなく、型の読み取り専用プロパティによって表されます。</span><span class="sxs-lookup"><span data-stu-id="2ef03-106">In the generated code, `repeated` fields are represented by read-only properties of the [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="2ef03-107">この型は、やなどのすべての標準 .NET コレクションインターフェイスを実装し <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601> ます。</span><span class="sxs-lookup"><span data-stu-id="2ef03-107">This type implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="2ef03-108">LINQ クエリを使用したり、配列またはリストに簡単に変換したりできます。</span><span class="sxs-lookup"><span data-stu-id="2ef03-108">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

<span data-ttu-id="2ef03-109">型には、 `RepeatedField<T>` リストをバイナリワイヤ形式にシリアル化および逆シリアル化するために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ef03-109">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span>

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
><span data-ttu-id="2ef03-110">[前へ](protobuf-nested-types.md)
>[次へ](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="2ef03-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>

---
title: リストと配列の繰り返しフィールド-WCF 開発者向けの gRPC
description: コレクションが Protobuf によってどのように処理され、.NET コレクションにどのように関連しているかを理解します。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841397"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="5fe9e-103">リストと配列の繰り返しフィールド</span><span class="sxs-lookup"><span data-stu-id="5fe9e-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="5fe9e-104">リストは、`repeated` prefix キーワードを使用して Protobuf で指定されます。</span><span class="sxs-lookup"><span data-stu-id="5fe9e-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="5fe9e-105">次の例は、リストを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fe9e-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="5fe9e-106">生成されたコードでは、`repeated` フィールドは、組み込みの .NET コレクション型ではなく、`Google.Protobuf.Collections.RepeatedField<T>` ジェネリック型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="5fe9e-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="5fe9e-107">`RepeatedField<T>` 型には、リストをバイナリワイヤ形式にシリアル化および逆シリアル化するために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fe9e-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="5fe9e-108"><xref:System.Collections.Generic.IList%601> や <xref:System.Collections.Generic.IEnumerable%601>などの標準的な .NET コレクションインターフェイスがすべて実装されているため、LINQ クエリを使用したり、配列やリストに簡単に変換したりできます。</span><span class="sxs-lookup"><span data-stu-id="5fe9e-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5fe9e-109">[前へ](protobuf-nested-types.md)
>[次へ](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="5fe9e-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>

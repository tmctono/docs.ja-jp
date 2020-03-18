---
title: リストと配列の繰り返しフィールド - WCF 開発者向け gRPC
description: Protobuf がコレクションを処理する方法と、コレクションと .NET コレクションとの関連について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147972"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="5e061-103">リストと配列の繰り返しフィールド</span><span class="sxs-lookup"><span data-stu-id="5e061-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="5e061-104">プレフィックス キーワードを使用して、プロトコル バッファー (Protobuf) でリストを`repeated`指定します。</span><span class="sxs-lookup"><span data-stu-id="5e061-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="5e061-105">次の例は、リストを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e061-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="5e061-106">生成されたコードでは、`repeated`フィールドは、組み`Google.Protobuf.Collections.RepeatedField<T>`込みの .NET コレクション型ではなく、ジェネリック型で表されます。</span><span class="sxs-lookup"><span data-stu-id="5e061-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="5e061-107">型`RepeatedField<T>`には、リストをシリアル化し、バイナリ ワイヤ形式に逆シリアル化するために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e061-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="5e061-108">標準の .NET コレクション インターフェイス<xref:System.Collections.Generic.IList%601>を実装します。 <xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5e061-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="5e061-109">そのため、LINQ クエリを使用したり、簡単に配列またはリストに変換したりできます。</span><span class="sxs-lookup"><span data-stu-id="5e061-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5e061-110">[前次](protobuf-nested-types.md)
>[Next](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="5e061-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>

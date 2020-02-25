---
title: リストと配列の繰り返しフィールド-WCF 開発者向けの gRPC
description: Protobuf がコレクションを処理する方法と、それらが .NET コレクションにどのように関連しているかを理解します。
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542960"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="7ccd2-103">リストと配列の繰り返しフィールド</span><span class="sxs-lookup"><span data-stu-id="7ccd2-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="7ccd2-104">プロトコルバッファー (Protobuf) でリストを指定するには、`repeated` prefix キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ccd2-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="7ccd2-105">次の例は、リストを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7ccd2-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="7ccd2-106">生成されたコードでは、`repeated` フィールドは、組み込みの .NET コレクション型ではなく、`Google.Protobuf.Collections.RepeatedField<T>` ジェネリック型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="7ccd2-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="7ccd2-107">`RepeatedField<T>` 型には、リストをバイナリワイヤ形式にシリアル化および逆シリアル化するために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ccd2-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="7ccd2-108"><xref:System.Collections.Generic.IList%601> や <xref:System.Collections.Generic.IEnumerable%601>など、すべての標準的な .NET コレクションインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="7ccd2-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="7ccd2-109">LINQ クエリを使用したり、配列またはリストに簡単に変換したりできます。</span><span class="sxs-lookup"><span data-stu-id="7ccd2-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7ccd2-110">[前へ](protobuf-nested-types.md)
>[次へ](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="7ccd2-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>

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
# <a name="repeated-fields-for-lists-and-arrays"></a>リストと配列の繰り返しフィールド

プレフィックスキーワードを使用して、プロトコルバッファー (Protobuf) でリストを指定し `repeated` ます。 次の例は、リストを作成する方法を示しています。

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

生成されたコードでは、 `repeated` フィールドは、 [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] 組み込みの .net コレクション型ではなく、型の読み取り専用プロパティによって表されます。 この型は、やなどのすべての標準 .NET コレクションインターフェイスを実装し <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601> ます。 LINQ クエリを使用したり、配列またはリストに簡単に変換したりできます。

型には、 `RepeatedField<T>` リストをバイナリワイヤ形式にシリアル化および逆シリアル化するために必要なコードが含まれています。

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
>[前へ](protobuf-nested-types.md)
>[次へ](protobuf-reserved.md)

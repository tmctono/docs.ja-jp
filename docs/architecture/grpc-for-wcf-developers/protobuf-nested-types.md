---
title: Protobuf 入れ子になった型-gRPC (WCF 開発者向け)
description: Protobuf と gRPC での入れ子になったメッセージの種類、およびでC#の生成方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 7b9a331336ebe1ca7bc75fdd164b7b88ae4f9db2
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542847"
---
# <a name="protobuf-nested-types"></a><span data-ttu-id="164b2-103">Protobuf 入れ子型</span><span class="sxs-lookup"><span data-stu-id="164b2-103">Protobuf nested types</span></span>

<span data-ttu-id="164b2-104">と同様C#に、他のクラス内でクラスを宣言できるのと同じように、プロトコルバッファー (Protobuf) を使用すると、メッセージ定義を他のメッセージ内に入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="164b2-104">Just as C# allows you to declare classes inside other classes, Protocol Buffer (Protobuf) allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="164b2-105">次の例は、入れ子になったメッセージ型を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="164b2-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="164b2-106">生成C#されたコードでは、`Inner` 型は `HelloRequest` クラス内の入れ子になった静的 `Types` クラスで宣言されます。</span><span class="sxs-lookup"><span data-stu-id="164b2-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="164b2-107">[前へ](protobuf-data-types.md)
>[次へ](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="164b2-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>

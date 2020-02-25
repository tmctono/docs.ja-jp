---
title: Protobuf の予約済みフィールド-WCF 開発者向け gRPC
description: バージョン間の互換性のために予約されているフィールドについて説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542977"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="6142d-103">Protobuf 予約フィールド</span><span class="sxs-lookup"><span data-stu-id="6142d-103">Protobuf reserved fields</span></span>

<span data-ttu-id="6142d-104">プロトコルバッファー (Protobuf) での下位互換性の保証は、常に同じデータ項目を表すフィールド番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="6142d-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="6142d-105">新しいバージョンのサービスでメッセージからフィールドが削除された場合、そのフィールド番号は再利用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6142d-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="6142d-106">これを行うには、`reserved` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6142d-106">You can enfore this by using the `reserved` keyword.</span></span> 

<span data-ttu-id="6142d-107">`displayName` フィールドと `marketId` フィールドが、前に定義した `Stock` メッセージから削除された場合は、次の例のようにフィールド番号を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6142d-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="6142d-108">また、今後追加される可能性のあるフィールドのプレースホルダーとして `reserved` キーワードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6142d-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="6142d-109">`to` キーワードを使用して、連続するフィールド番号を範囲として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="6142d-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="6142d-110">[前へ](protobuf-repeated.md)
>[次へ](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="6142d-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>

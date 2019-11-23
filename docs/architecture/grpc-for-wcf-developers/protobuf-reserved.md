---
title: Protobuf の予約済みフィールド-WCF 開発者向け gRPC
description: バージョン間の互換性のために予約されているフィールドについて説明します。
ms.date: 09/09/2019
ms.openlocfilehash: e589cd38a712ce014fa2c4d847fbde359d538dd0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967314"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="57830-103">Protobuf 予約フィールド</span><span class="sxs-lookup"><span data-stu-id="57830-103">Protobuf reserved fields</span></span>

<span data-ttu-id="57830-104">Protobuf の下位互換性の保証は、常に同じデータ項目を表すフィールド番号に依存しています。</span><span class="sxs-lookup"><span data-stu-id="57830-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="57830-105">新しいバージョンのサービスでメッセージからフィールドが削除された場合、そのフィールド番号は再利用しないでください。</span><span class="sxs-lookup"><span data-stu-id="57830-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="57830-106">これは、`reserved` キーワードを使用して適用できます。</span><span class="sxs-lookup"><span data-stu-id="57830-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="57830-107">`displayName` フィールドと `marketId` フィールドが、前に定義した `Stock` メッセージから削除された場合は、次の例のようにフィールド番号を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57830-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="57830-108">`reserved` キーワードは、今後追加される可能性のあるフィールドのプレースホルダーとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="57830-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="57830-109">連続したフィールド番号は、`to` キーワードを使用して範囲として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="57830-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="57830-110">[前へ](protobuf-repeated.md)
>[次へ](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="57830-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>

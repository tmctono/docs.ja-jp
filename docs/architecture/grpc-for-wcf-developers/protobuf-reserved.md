---
title: プロトブーフ予約フィールド - WCF 開発者向け gRPC
description: バージョン間の互換性のために予約済みのフィールドについて説明します。
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111037"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="90834-103">Protobuf 予約フィールド</span><span class="sxs-lookup"><span data-stu-id="90834-103">Protobuf reserved fields</span></span>

<span data-ttu-id="90834-104">プロトコル バッファ (Protobuf) の下位互換性保証は、常に同じデータ項目を表すフィールド番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="90834-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="90834-105">新しいバージョンのサービスでメッセージからフィールドを削除した場合、そのフィールド番号は再利用されません。</span><span class="sxs-lookup"><span data-stu-id="90834-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="90834-106">キーワードを使用`reserved`して、これを適用できます。</span><span class="sxs-lookup"><span data-stu-id="90834-106">You can enforce this by using the `reserved` keyword.</span></span>

<span data-ttu-id="90834-107">フィールドと`displayName``marketId`フィールドが、前に`Stock`定義したメッセージから削除された場合、フィールド番号は次の例のように予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90834-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="90834-108">また、キーワードは`reserved`、将来追加される可能性のあるフィールドのプレースホルダーとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="90834-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="90834-109">`to`キーワードを使用して、連続するフィールド番号を範囲として表現できます。</span><span class="sxs-lookup"><span data-stu-id="90834-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="90834-110">[前次](protobuf-repeated.md)
>[Next](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="90834-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>

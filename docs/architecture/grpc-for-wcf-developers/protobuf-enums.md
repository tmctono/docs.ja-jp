---
title: Protobuf 列挙型-WCF 開発者向け gRPC
description: Protobuf で列挙型を宣言して使用する方法について説明します。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f18196f54caba824d7101782a88cf3bf699560d5
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841415"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="fee7e-103">Protobuf 列挙型</span><span class="sxs-lookup"><span data-stu-id="fee7e-103">Protobuf enumerations</span></span>

<span data-ttu-id="fee7e-104">Protobuf は列挙型をサポートしています。前のセクションでは、列挙型を使用して `oneof` フィールドの型を決定しています。</span><span class="sxs-lookup"><span data-stu-id="fee7e-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="fee7e-105">独自の列挙型を定義すると、Protobuf は列挙型C#にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="fee7e-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="fee7e-106">Protobuf は異なる言語で使用できるため、列挙型の名前付け規則は規則とC#は異なります。</span><span class="sxs-lookup"><span data-stu-id="fee7e-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="fee7e-107">ただし、コードジェネレーターは巧妙で、名前を従来C#のケースに変換します。</span><span class="sxs-lookup"><span data-stu-id="fee7e-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="fee7e-108">フィールド名に対応する Pascal 形式が列挙名で始まる場合は、その名前が削除されます。</span><span class="sxs-lookup"><span data-stu-id="fee7e-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="fee7e-109">たとえば、この Protobuf 列挙型では、フィールドの先頭に `ACCOUNT_STATUS`が付きます。これは、Pascal 形式の enum name: `AccountStatus`と同じです。</span><span class="sxs-lookup"><span data-stu-id="fee7e-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="fee7e-110">そのため、ジェネレーターは、 C#次のコードと同等の列挙型を作成します。</span><span class="sxs-lookup"><span data-stu-id="fee7e-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

<span data-ttu-id="fee7e-111">Protobuf 列挙型の定義には、最初のフィールドとして0の定数を**指定しなければなりません**。</span><span class="sxs-lookup"><span data-stu-id="fee7e-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="fee7e-112">C#と同様に、同じ値を持つ複数のフィールドを宣言できますが、列挙型の `allow_alias` オプションを使用して、このオプションを明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee7e-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

<span data-ttu-id="fee7e-113">列挙は、`.proto` ファイルの最上位レベルで宣言することも、メッセージ定義内で入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fee7e-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="fee7e-114">入れ子になったメッセージと同様に、入れ子になった列挙型は、生成された message クラスの `.Types` 静的クラス内で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="fee7e-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="fee7e-115">Protobuf で生成された列挙型に[[Flags]](xref:System.FlagsAttribute)属性を適用する方法はありません。 Protobuf はビットごとの列挙の組み合わせを認識しません。</span><span class="sxs-lookup"><span data-stu-id="fee7e-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="fee7e-116">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="fee7e-116">Take a look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

<span data-ttu-id="fee7e-117">`product.AvailableIn` を `Region.NorthAmerica | Region.SouthAmerica`に設定すると、`3`整数値としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="fee7e-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="fee7e-118">クライアントまたはサーバーが値を逆シリアル化しようとすると、`3` の列挙型の定義に一致するものが見つからず、結果が `Region.None`されます。</span><span class="sxs-lookup"><span data-stu-id="fee7e-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="fee7e-119">Protobuf で複数の列挙値を操作する最善の方法は、列挙型の `repeated` フィールドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="fee7e-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fee7e-120">[前へ](protobuf-any-oneof.md)
>[次へ](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="fee7e-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>

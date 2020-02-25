---
title: Protobuf 列挙型-WCF 開発者向け gRPC
description: Protobuf で列挙型を宣言して使用する方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543145"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="ca469-103">Protobuf 列挙型</span><span class="sxs-lookup"><span data-stu-id="ca469-103">Protobuf enumerations</span></span>

<span data-ttu-id="ca469-104">Protobuf は列挙型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ca469-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="ca469-105">前のセクションでこのサポートを確認しました。ここでは、列挙型を使用して `Oneof` フィールドの型を決定しました。</span><span class="sxs-lookup"><span data-stu-id="ca469-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="ca469-106">独自の列挙型を定義すると、Protobuf は列挙型にC#コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ca469-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="ca469-107">さまざまな言語で Protobuf を使用できるため、列挙型の名前付け規則は規則C#とは異なります。</span><span class="sxs-lookup"><span data-stu-id="ca469-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="ca469-108">ただし、コードジェネレーターは、名前を従来C#のケースに変換します。</span><span class="sxs-lookup"><span data-stu-id="ca469-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="ca469-109">フィールド名に対応する Pascal 形式が列挙名で始まる場合は、その名前が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca469-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="ca469-110">たとえば、次の Protobuf 列挙では、フィールドの先頭に `ACCOUNT_STATUS`が付きます。</span><span class="sxs-lookup"><span data-stu-id="ca469-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="ca469-111">このプレフィックスは、Pascal 形式の列挙名、`AccountStatus`に相当します。</span><span class="sxs-lookup"><span data-stu-id="ca469-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="ca469-112">ジェネレーターは、次C#のコードと同等の列挙型を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca469-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="ca469-113">Protobuf 列挙型の定義には、最初のフィールドとして0の定数を*指定しなければなりません*。</span><span class="sxs-lookup"><span data-stu-id="ca469-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="ca469-114">と同様C#に、同じ値を持つ複数のフィールドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="ca469-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="ca469-115">ただし、列挙型の `allow_alias` オプションを使用して、このオプションを明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca469-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="ca469-116">列挙は、`.proto` ファイルの最上位レベルで宣言することも、メッセージ定義内で入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ca469-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="ca469-117">入れ子になったメッセージと同様に、入れ子になった列挙型は、生成された message クラスの `.Types` 静的クラス内で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="ca469-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="ca469-118">Protobuf で生成された列挙型に[[Flags]](xref:System.FlagsAttribute)属性を適用する方法はありません。 Protobuf はビットごとの列挙の組み合わせを認識しません。</span><span class="sxs-lookup"><span data-stu-id="ca469-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="ca469-119">次の例を見てください。</span><span class="sxs-lookup"><span data-stu-id="ca469-119">Look at the following example:</span></span>

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

<span data-ttu-id="ca469-120">`product.AvailableIn` を `Region.NorthAmerica | Region.SouthAmerica`に設定すると、`3`整数値としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="ca469-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="ca469-121">クライアントまたはサーバーが値を逆シリアル化しようとすると、`3`の列挙型の定義に一致するものが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="ca469-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="ca469-122">結果は `Region.None`になります。</span><span class="sxs-lookup"><span data-stu-id="ca469-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="ca469-123">Protobuf で複数の列挙値を操作する最善の方法は、列挙型の `repeated` フィールドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="ca469-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ca469-124">[前へ](protobuf-any-oneof.md)
>[次へ](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="ca469-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>

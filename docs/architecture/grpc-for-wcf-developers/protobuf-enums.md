---
title: プロトブーフ列挙 - WCF 開発者向け gRPC
description: Protobuf で列挙体を宣言して使用する方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148076"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="36e74-103">Protobuf 列挙型</span><span class="sxs-lookup"><span data-stu-id="36e74-103">Protobuf enumerations</span></span>

<span data-ttu-id="36e74-104">Protobuf は列挙型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="36e74-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="36e74-105">前のセクションでは、フィールドの種類を決定するために列挙型を使用したこのサポートを`Oneof`確認しました。</span><span class="sxs-lookup"><span data-stu-id="36e74-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="36e74-106">独自の列挙型を定義すると、Protobuf は C# 列挙型にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="36e74-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="36e74-107">Protobuf はさまざまな言語で使用できるため、列挙体の名前付け規則は C# の規則とは異なります。</span><span class="sxs-lookup"><span data-stu-id="36e74-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="36e74-108">ただし、コード ジェネレーターは、名前を従来の C# の大文字と小文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="36e74-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="36e74-109">フィールド名の Pascal の大文字と小文字の対応が列挙名で始まる場合は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="36e74-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="36e74-110">たとえば、次の Protobuf 列挙体では、フィールドの先頭に`ACCOUNT_STATUS`.</span><span class="sxs-lookup"><span data-stu-id="36e74-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="36e74-111">このプレフィックスは、パスカルケースの列挙名と`AccountStatus`同じです。</span><span class="sxs-lookup"><span data-stu-id="36e74-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="36e74-112">ジェネレーターは、次のコードと同等の C# 列挙型を作成します。</span><span class="sxs-lookup"><span data-stu-id="36e74-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="36e74-113">Protobuf 列挙型の定義は、最初のフィールドとしてゼロ定数を持つ*必要があります*。</span><span class="sxs-lookup"><span data-stu-id="36e74-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="36e74-114">C# と同様に、同じ値を持つ複数のフィールドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="36e74-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="36e74-115">ただし、列挙型のオプションを使用して、この`allow_alias`オプションを明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36e74-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="36e74-116">列挙型は`.proto`、ファイルの最上位レベルで宣言するか、メッセージ定義内で入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="36e74-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="36e74-117">入れ子になったメッセージなどの入れ子になった列挙型は、生成`.Types`されたメッセージ クラスの静的クラス内で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="36e74-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="36e74-118">プロトブーフで生成された列挙型に[[Flags]](xref:System.FlagsAttribute)属性を適用する方法はなく、Protobuf はビットごとの列挙型の組み合わせを理解していません。</span><span class="sxs-lookup"><span data-stu-id="36e74-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="36e74-119">次の例を見てください。</span><span class="sxs-lookup"><span data-stu-id="36e74-119">Look at the following example:</span></span>

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

<span data-ttu-id="36e74-120">に`product.AvailableIn``Region.NorthAmerica | Region.SouthAmerica`設定すると、整数値としてシリアル化されます`3`。</span><span class="sxs-lookup"><span data-stu-id="36e74-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="36e74-121">クライアントまたはサーバーが値を逆シリアル化しようとすると、`3`の enum 定義に一致するものが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="36e74-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="36e74-122">結果は`Region.None`.</span><span class="sxs-lookup"><span data-stu-id="36e74-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="36e74-123">Protobuf で複数の列挙値を操作する最善の方法は、`repeated`列挙型のフィールドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="36e74-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="36e74-124">[前次](protobuf-any-oneof.md)
>[Next](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="36e74-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>

---
title: プロトブーフ スカラー データ型 - WCF 開発者向け gRPC
description: NET Core で Protobuf および gRPC がサポートする基本的なデータ型と既知のデータ型について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: ea3b53426ecf6f50f3bae22a537e227b07248508
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249436"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="09a36-103">Protobuf スカラー データ型</span><span class="sxs-lookup"><span data-stu-id="09a36-103">Protobuf scalar data types</span></span>

<span data-ttu-id="09a36-104">プロトコル バッファ (Protobuf) は、ネイティブスカラー値の種類の範囲をサポートします。</span><span class="sxs-lookup"><span data-stu-id="09a36-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="09a36-105">次の表は、それらすべてを同等の C# 型と共に示しています。</span><span class="sxs-lookup"><span data-stu-id="09a36-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="09a36-106">プロトブーフタイプ</span><span class="sxs-lookup"><span data-stu-id="09a36-106">Protobuf type</span></span> | <span data-ttu-id="09a36-107">C# 型</span><span class="sxs-lookup"><span data-stu-id="09a36-107">C# type</span></span>      | <span data-ttu-id="09a36-108">Notes</span><span class="sxs-lookup"><span data-stu-id="09a36-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="09a36-109">1</span><span class="sxs-lookup"><span data-stu-id="09a36-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="09a36-110">1</span><span class="sxs-lookup"><span data-stu-id="09a36-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="09a36-111">1</span><span class="sxs-lookup"><span data-stu-id="09a36-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="09a36-112">1</span><span class="sxs-lookup"><span data-stu-id="09a36-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="09a36-113">2</span><span class="sxs-lookup"><span data-stu-id="09a36-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="09a36-114">2</span><span class="sxs-lookup"><span data-stu-id="09a36-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="09a36-115">2</span><span class="sxs-lookup"><span data-stu-id="09a36-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="09a36-116">2</span><span class="sxs-lookup"><span data-stu-id="09a36-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="09a36-117">3</span><span class="sxs-lookup"><span data-stu-id="09a36-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="09a36-118">4</span><span class="sxs-lookup"><span data-stu-id="09a36-118">4</span></span>     |

<span data-ttu-id="09a36-119">注:</span><span class="sxs-lookup"><span data-stu-id="09a36-119">Notes:</span></span>

1. <span data-ttu-id="09a36-120">署名付`int32`き`int64`の値を使用する場合は、標準エンコードは非効率的です。</span><span class="sxs-lookup"><span data-stu-id="09a36-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="09a36-121">フィールドに負の数が含まれる可能性がある場合`sint32`は`sint64`、またはを使用します。</span><span class="sxs-lookup"><span data-stu-id="09a36-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="09a36-122">これらの型は、それぞれ`int`C#`long`と型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="09a36-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="09a36-123">フィールド`fixed`は、値が何であるかに関係なく、常に同じバイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="09a36-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="09a36-124">この動作により、シリアル化と逆シリアル化が大きい値に対して高速になります。</span><span class="sxs-lookup"><span data-stu-id="09a36-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="09a36-125">プロトブフ文字列は UTF-8 (または 7 ビット ASCII) でエンコードされています。</span><span class="sxs-lookup"><span data-stu-id="09a36-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="09a36-126">エンコードされた長さは 2<sup>32</sup>より大きくすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09a36-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="09a36-127">Protobuf ランタイムは、C#`ByteString``byte[]`配列との間で簡単にマップする型を提供します。</span><span class="sxs-lookup"><span data-stu-id="09a36-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="09a36-128">その他の .NET プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="09a36-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="09a36-129">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="09a36-129">Dates and times</span></span>

<span data-ttu-id="09a36-130">ネイティブ スカラー型は、日付<xref:System.DateTimeOffset>と時刻の値<xref:System.DateTime>を提供しません。 <xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="09a36-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="09a36-131">Google の「よく知られているタイプ」の拡張機能を使用して、これらのタイプを指定できます。</span><span class="sxs-lookup"><span data-stu-id="09a36-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="09a36-132">これらの拡張機能は、サポートされているプラットフォーム全体で、複雑なフィールド型のコード生成とランタイムサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="09a36-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="09a36-133">次の表は、日付と時刻の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="09a36-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="09a36-134">C# 型</span><span class="sxs-lookup"><span data-stu-id="09a36-134">C# type</span></span> | <span data-ttu-id="09a36-135">プロトブーフの有名なタイプ</span><span class="sxs-lookup"><span data-stu-id="09a36-135">Protobuf well-known type</span></span> |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

<span data-ttu-id="09a36-136">C# クラスで生成されるプロパティは、.NET の日付と時刻の型ではありません。</span><span class="sxs-lookup"><span data-stu-id="09a36-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="09a36-137">プロパティは、名前空間`Timestamp`内`Duration`の クラス`Google.Protobuf.WellKnownTypes`と クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="09a36-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="09a36-138">これらのクラスは、 `DateTimeOffset`、 `DateTime`、および との`TimeSpan`間で変換するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="09a36-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> <span data-ttu-id="09a36-139">この`Timestamp`型は UTC 時刻で動作します。</span><span class="sxs-lookup"><span data-stu-id="09a36-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="09a36-140">`DateTimeOffset`値は常にゼロのオフセットを`DateTime.Kind`持ち、プロパティは`DateTimeKind.Utc`常に です。</span><span class="sxs-lookup"><span data-stu-id="09a36-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="09a36-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="09a36-141">System.Guid</span></span>

<span data-ttu-id="09a36-142">Protobuf は、他のプラットフォーム<xref:System.Guid>と呼ばれる`UUID`型を直接サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="09a36-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="09a36-143">よく知られているタイプはありません。</span><span class="sxs-lookup"><span data-stu-id="09a36-143">There's no well-known type for it.</span></span>

<span data-ttu-id="09a36-144">最適な方法は、標準`Guid``string``8-4-4-4-12`の 16 進形式 (たとえば)`45a9fda3-bd01-47a9-8460-c1cd7484b0b3`を使用して、値をフィールドとして処理することです。</span><span class="sxs-lookup"><span data-stu-id="09a36-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="09a36-145">すべての言語とプラットフォームは、その形式を解析できます。</span><span class="sxs-lookup"><span data-stu-id="09a36-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="09a36-146">`Guid`値にフィールドを`bytes`使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="09a36-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="09a36-147">Protobuf が Java などの他のプラットフォームと対話しているとき、*エンディアンネス*([Wikipedia 定義](https://en.wikipedia.org/wiki/Endianness)) の問題は、不安定な動作を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09a36-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="09a36-148">Null 許容型</span><span class="sxs-lookup"><span data-stu-id="09a36-148">Nullable types</span></span>

<span data-ttu-id="09a36-149">C# の Protobuf コード生成では、`int`ネイティブ型を使用`int32`します。</span><span class="sxs-lookup"><span data-stu-id="09a36-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="09a36-150">したがって、値は常に含まれ、null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09a36-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="09a36-151">C# コードでの使用`int?`など、明示的な null を必要とする値の場合、Protobuf の "既知の型" には、null 許容 C# 型にコンパイルされるラッパーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09a36-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="09a36-152">これらを使用するには、次`wrappers.proto`のように`.proto`ファイルにインポートします。</span><span class="sxs-lookup"><span data-stu-id="09a36-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="09a36-153">Protobuf は、生成`T?`されたメッセージ プロパティ`int?`に単純な ( など ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="09a36-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="09a36-154">次の表は、同等の C# 型を持つラッパー型の完全な一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="09a36-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="09a36-155">C# 型</span><span class="sxs-lookup"><span data-stu-id="09a36-155">C# type</span></span>   | <span data-ttu-id="09a36-156">よく知られている型ラッパー</span><span class="sxs-lookup"><span data-stu-id="09a36-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="09a36-157">よく知られている型`Timestamp`と`Duration`クラスとして .NET で表されます。</span><span class="sxs-lookup"><span data-stu-id="09a36-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="09a36-158">C# 8 以降では、null 許容参照型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="09a36-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="09a36-159">しかし、これらの型のプロパティを null に変換する場合は、これらの型のプロパティ`DateTimeOffset`を`TimeSpan`チェックすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="09a36-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="09a36-160">10 進数</span><span class="sxs-lookup"><span data-stu-id="09a36-160">Decimals</span></span>

<span data-ttu-id="09a36-161">Protobuf は.NET`decimal`型を`double`ネイティブにサポートしていません。 `float`</span><span class="sxs-lookup"><span data-stu-id="09a36-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="09a36-162">Protobuf プロジェクトでは、標準型をサポートする言語やフレームワークのプラットフォームサポートを`Decimal`使用して、既知の型に標準型を追加する可能性について、継続的な議論が行われています。</span><span class="sxs-lookup"><span data-stu-id="09a36-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="09a36-163">まだ何も実装されていません。</span><span class="sxs-lookup"><span data-stu-id="09a36-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="09a36-164">.NET クライアントとサーバー間の安全なシリアル化`decimal`に使用する型を表すメッセージ定義を作成できます。</span><span class="sxs-lookup"><span data-stu-id="09a36-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="09a36-165">しかし、他のプラットフォームの開発者は、使用されている形式を理解し、独自の処理を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a36-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="09a36-166">Protobuf のカスタム 10 進型の作成</span><span class="sxs-lookup"><span data-stu-id="09a36-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="09a36-167">単純な実装は、フィールドを使用しない一`Money`部の Google API が使用する`currency`非標準型に似ている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09a36-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

<span data-ttu-id="09a36-168">この`nanos`フィールドは、`0.999_999_999`から`-0.999_999_999`から への値を表します。</span><span class="sxs-lookup"><span data-stu-id="09a36-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="09a36-169">たとえば、`decimal`値`1.5m`は`{ units = 1, nanos = 500_000_000 }`として表されます。</span><span class="sxs-lookup"><span data-stu-id="09a36-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="09a36-170">この例の`nanos`フィールドでは、大きな値よりも`sfixed32``int32`効率的にエンコードされる型を使用するのはこのためです。</span><span class="sxs-lookup"><span data-stu-id="09a36-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="09a36-171">フィールドが`units`負の場合、`nanos`フィールドも負の値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a36-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="09a36-172">バイト文字列として値をエンコード`decimal`するためのアルゴリズムは他に複数ありますが、このメッセージはそれらよりも理解しやすいです。</span><span class="sxs-lookup"><span data-stu-id="09a36-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="09a36-173">値は、異なるプラットフォームでのエンディアンの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="09a36-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="09a36-174">この型と BCL`decimal`型の間の変換は、C# で次のように実装できます。</span><span class="sxs-lookup"><span data-stu-id="09a36-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="09a36-175">このようなカスタム メッセージタイプを*使用する場合*は、常に`.proto`.</span><span class="sxs-lookup"><span data-stu-id="09a36-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="09a36-176">その後、他の開発者は、対応する型との変換を、独自の言語またはフレームワークで実装できます。</span><span class="sxs-lookup"><span data-stu-id="09a36-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="09a36-177">[前次](protobuf-messages.md)
>[Next](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="09a36-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>

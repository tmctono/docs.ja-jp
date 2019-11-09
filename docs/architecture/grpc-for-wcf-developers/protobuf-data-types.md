---
title: Protobuf スカラーデータ型-gRPC (WCF 開発者向け)
description: .NET Core の Protobuf と gRPC でサポートされている基本的なデータ型と既知のデータ型について説明します。
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: cae9cc483ffb791a9b53e6a2d9d7c0924d725a67
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841457"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="f8d39-103">Protobuf スカラー データ型</span><span class="sxs-lookup"><span data-stu-id="f8d39-103">Protobuf scalar data types</span></span>

<span data-ttu-id="f8d39-104">Protobuf は、ネイティブスカラー値型の範囲をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f8d39-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="f8d39-105">次の表に、それらのすべてのC#型に対応する型を示します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="f8d39-106">Protobuf 型</span><span class="sxs-lookup"><span data-stu-id="f8d39-106">Protobuf type</span></span> | <span data-ttu-id="f8d39-107">C# 型</span><span class="sxs-lookup"><span data-stu-id="f8d39-107">C# type</span></span>      | <span data-ttu-id="f8d39-108">ノート</span><span class="sxs-lookup"><span data-stu-id="f8d39-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="f8d39-109">1</span><span class="sxs-lookup"><span data-stu-id="f8d39-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="f8d39-110">1</span><span class="sxs-lookup"><span data-stu-id="f8d39-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="f8d39-111">1</span><span class="sxs-lookup"><span data-stu-id="f8d39-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="f8d39-112">1</span><span class="sxs-lookup"><span data-stu-id="f8d39-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="f8d39-113">2</span><span class="sxs-lookup"><span data-stu-id="f8d39-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="f8d39-114">2</span><span class="sxs-lookup"><span data-stu-id="f8d39-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="f8d39-115">2</span><span class="sxs-lookup"><span data-stu-id="f8d39-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="f8d39-116">2</span><span class="sxs-lookup"><span data-stu-id="f8d39-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="f8d39-117">3</span><span class="sxs-lookup"><span data-stu-id="f8d39-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="f8d39-118">4</span><span class="sxs-lookup"><span data-stu-id="f8d39-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="f8d39-119">ノート</span><span class="sxs-lookup"><span data-stu-id="f8d39-119">Notes</span></span>

1. <span data-ttu-id="f8d39-120">`int32` および `int64` の標準エンコードは、署名された値を使用する場合には非効率的です。</span><span class="sxs-lookup"><span data-stu-id="f8d39-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="f8d39-121">フィールドに負の数値が含まれている可能性がある場合は、代わりに `sint32` または `sint64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="f8d39-122">両方の型はC# 、それぞれ `int` と `long` 型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="f8d39-123">`fixed` のフィールドでは、値が何であるかにかかわらず、常に同じバイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="f8d39-124">この動作により、シリアル化と逆シリアル化がより大きな値に対して高速化されます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="f8d39-125">Protobuf 文字列は UTF-8 (または7ビット ASCII) でエンコードされ、エンコードされた長さは 2<sup>32</sup>を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="f8d39-126">Protobuf ランタイムには、`byte[]` 配列との間C#で簡単にマップできる `ByteString` 型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f8d39-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="f8d39-127">その他の .NET プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="f8d39-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="f8d39-128">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="f8d39-128">Dates and times</span></span>

<span data-ttu-id="f8d39-129">ネイティブスカラー型では、日付と時刻の値が提供さC#れません。これは、の <xref:System.DateTimeOffset>、<xref:System.DateTime>、および <xref:System.TimeSpan>と同じです。</span><span class="sxs-lookup"><span data-stu-id="f8d39-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="f8d39-130">これらの型は、Google の "既知の型" 拡張機能の一部を使用して指定できます。これにより、サポートされているプラットフォーム全体で、より複雑なフィールド型に対するコード生成とランタイムサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="f8d39-131">次の表は、日付と時刻の型を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8d39-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="f8d39-132">C# 型</span><span class="sxs-lookup"><span data-stu-id="f8d39-132">C# type</span></span> | <span data-ttu-id="f8d39-133">Protobuf 既知の型</span><span class="sxs-lookup"><span data-stu-id="f8d39-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="f8d39-134">C#クラスで生成されるプロパティは、.net の日付型と時刻型ではありません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="f8d39-135">プロパティは、`DateTimeOffset`、`DateTime`、および `TimeSpan`との間で変換を行うためのメソッドを提供する、`Google.Protobuf.WellKnownTypes` 名前空間の `Timestamp` クラスと `Duration` クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="f8d39-136">`Timestamp` 型は UTC 時刻で動作します。`DateTimeOffset` 値は常に0のオフセットを持ち、`DateTime.Kind` プロパティは常に `DateTimeKind.Utc`になります。</span><span class="sxs-lookup"><span data-stu-id="f8d39-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="f8d39-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="f8d39-137">System.Guid</span></span>

<span data-ttu-id="f8d39-138">他のプラットフォームで `UUID` として知られている <xref:System.Guid> の種類は、Protobuf によって直接サポートされておらず、既知の型もありません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="f8d39-139">最適な方法は、標準 `8-4-4-4-12` 16 進数形式 (`45a9fda3-bd01-47a9-8460-c1cd7484b0b3`など) を使用して `Guid` 値を `string` フィールドとして処理することです。これは、すべての言語とプラットフォームで解析できます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="f8d39-140">`Guid` 値には `bytes` フィールドを使用しないでください。これにより、エンディアンの問題により、Java などの他のプラットフォームとの対話で動作が不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8d39-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="f8d39-141">Null 許容型</span><span class="sxs-lookup"><span data-stu-id="f8d39-141">Nullable types</span></span>

<span data-ttu-id="f8d39-142">のC# Protobuf コード生成では、`int32`の `int` などのネイティブ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="f8d39-143">つまり、値は常に含まれ、null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="f8d39-144">C#コードで `int?` を使用するなど、明示的な null を必要とする値の場合、Protobuf の "既知の型" にはC# 、null 許容型にコンパイルされるラッパーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="f8d39-145">これらを使用するには、次のように `wrappers.proto` を `.proto` ファイルにインポートします。</span><span class="sxs-lookup"><span data-stu-id="f8d39-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="f8d39-146">Protobuf は、生成されたメッセージプロパティに simple `T?` (`int?`など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="f8d39-147">次の表に、ラッパー型とそれに対応C#する型の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="f8d39-148">C# 型</span><span class="sxs-lookup"><span data-stu-id="f8d39-148">C# type</span></span>   | <span data-ttu-id="f8d39-149">既知の型ラッパー</span><span class="sxs-lookup"><span data-stu-id="f8d39-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="f8d39-150">既知の型 `Timestamp` と `Duration` は、クラスとして .NET で表現されるため、null 許容バージョンを必要としませんが `DateTimeOffset` または `TimeSpan`に変換するときに、これらの型のプロパティで null をチェックすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="f8d39-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="f8d39-151">数点</span><span class="sxs-lookup"><span data-stu-id="f8d39-151">Decimals</span></span>

<span data-ttu-id="f8d39-152">Protobuf は、.NET `decimal` 型をネイティブでサポートしていません。 `double` と `float`だけです。</span><span class="sxs-lookup"><span data-stu-id="f8d39-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="f8d39-153">Protobuf プロジェクトでは、標準 `Decimal` 型を既知の型に追加することができますが、それをサポートする言語とフレームワークはプラットフォームでサポートされていますが、まだ実装されていません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="f8d39-154">.NET クライアントとサーバー間の安全なシリアル化に使用できる `decimal` 型を表すメッセージ定義を作成することはできますが、他のプラットフォームの開発者は、使用されている形式を理解し、独自の処理を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8d39-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="f8d39-155">Protobuf のカスタム Decimal 型の作成</span><span class="sxs-lookup"><span data-stu-id="f8d39-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="f8d39-156">非常に単純な実装は、一部の Google Api で使用される非標準の `Money` 型に似ていますが、`currency` フィールドはありません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="f8d39-157">`nanos` フィールドは、`0.999_999_999` から `-0.999_999_999`までの値を表します。</span><span class="sxs-lookup"><span data-stu-id="f8d39-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="f8d39-158">たとえば、`decimal` 値 `1.5m` は `{ units = 1, nanos = 500_000_000 }` として表されます (この例の `nanos` フィールドでは、より大きな値に対して `sfixed32` よりも効率的にエンコードされる `int32` 型を使用しています)。</span><span class="sxs-lookup"><span data-stu-id="f8d39-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="f8d39-159">`units` フィールドが負の値の場合、`nanos` フィールドにも負の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8d39-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="f8d39-160">`decimal` 値をバイト文字列としてエンコードするためのアルゴリズムは他にもいくつかありますが、このメッセージはどのようなものでも理解しやすく、異なるプラットフォームの *[エンディアン](https://en.wikipedia.org/wiki/Endianness)* の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="f8d39-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="f8d39-161">この型と BCL `decimal` 型の間の変換は、次C#のようにで実装できます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="f8d39-162">このようなカスタムユーティリティメッセージ型を使用する場合は常に、他の開発者が独自の言語またはフレームワークで同等の型との間で変換を実装できるように、`.proto` にコメントを付けて文書化**する必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="f8d39-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f8d39-163">[前へ](protobuf-messages.md)
>[次へ](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="f8d39-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>

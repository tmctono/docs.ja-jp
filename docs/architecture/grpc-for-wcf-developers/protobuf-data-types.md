---
title: Protobuf スカラーデータ型-gRPC (WCF 開発者向け)
description: .NET Core で Protobuf と gRPC がサポートする基本データ型と既知のデータ型について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543158"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="7d305-103">Protobuf スカラー データ型</span><span class="sxs-lookup"><span data-stu-id="7d305-103">Protobuf scalar data types</span></span>

<span data-ttu-id="7d305-104">プロトコルバッファー (Protobuf) は、ネイティブスカラー値型の範囲をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7d305-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="7d305-105">次の表に、それらのすべてのC#型に対応する型を示します。</span><span class="sxs-lookup"><span data-stu-id="7d305-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="7d305-106">Protobuf 型</span><span class="sxs-lookup"><span data-stu-id="7d305-106">Protobuf type</span></span> | <span data-ttu-id="7d305-107">C# 型</span><span class="sxs-lookup"><span data-stu-id="7d305-107">C# type</span></span>      | <span data-ttu-id="7d305-108">メモ</span><span class="sxs-lookup"><span data-stu-id="7d305-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="7d305-109">1</span><span class="sxs-lookup"><span data-stu-id="7d305-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="7d305-110">1</span><span class="sxs-lookup"><span data-stu-id="7d305-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="7d305-111">1</span><span class="sxs-lookup"><span data-stu-id="7d305-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="7d305-112">1</span><span class="sxs-lookup"><span data-stu-id="7d305-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="7d305-113">2</span><span class="sxs-lookup"><span data-stu-id="7d305-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="7d305-114">2</span><span class="sxs-lookup"><span data-stu-id="7d305-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="7d305-115">2</span><span class="sxs-lookup"><span data-stu-id="7d305-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="7d305-116">2</span><span class="sxs-lookup"><span data-stu-id="7d305-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="7d305-117">3</span><span class="sxs-lookup"><span data-stu-id="7d305-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="7d305-118">4</span><span class="sxs-lookup"><span data-stu-id="7d305-118">4</span></span>     |

<span data-ttu-id="7d305-119">注:</span><span class="sxs-lookup"><span data-stu-id="7d305-119">Notes:</span></span>

1. <span data-ttu-id="7d305-120">`int32` と `int64` の標準エンコードは、署名された値を操作するときには非効率的です。</span><span class="sxs-lookup"><span data-stu-id="7d305-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="7d305-121">フィールドに負の数値が含まれている可能性がある場合は、代わりに `sint32` または `sint64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d305-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="7d305-122">これらの型はC# 、それぞれ `int` および `long` 型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="7d305-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="7d305-123">`fixed` のフィールドでは、値が何であるかにかかわらず、常に同じバイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d305-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="7d305-124">この動作により、シリアル化と逆シリアル化がより大きな値に対して高速化されます。</span><span class="sxs-lookup"><span data-stu-id="7d305-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="7d305-125">Protobuf 文字列は、UTF-8 (または7ビット ASCII) でエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="7d305-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="7d305-126">エンコードされた長さは 2<sup>32</sup>を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d305-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="7d305-127">Protobuf ランタイムには、`byte[]` 配列との間C#で簡単にマップできる `ByteString` 型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d305-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="7d305-128">その他の .NET プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="7d305-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="7d305-129">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="7d305-129">Dates and times</span></span>

<span data-ttu-id="7d305-130">ネイティブスカラー型では、日付と時刻の値が提供さC#れません。これは、の <xref:System.DateTimeOffset>、<xref:System.DateTime>、および <xref:System.TimeSpan>と同じです。</span><span class="sxs-lookup"><span data-stu-id="7d305-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="7d305-131">これらの型は、Google の "既知の型" 拡張機能を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d305-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="7d305-132">これらの拡張機能は、サポートされるプラットフォーム全体で、複雑なフィールド型に対するコード生成とランタイムサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d305-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="7d305-133">次の表は、日付と時刻の型を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d305-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="7d305-134">C# 型</span><span class="sxs-lookup"><span data-stu-id="7d305-134">C# type</span></span> | <span data-ttu-id="7d305-135">Protobuf 既知の型</span><span class="sxs-lookup"><span data-stu-id="7d305-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="7d305-136">C#クラスで生成されるプロパティは、.net の日付型と時刻型ではありません。</span><span class="sxs-lookup"><span data-stu-id="7d305-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="7d305-137">プロパティは、`Google.Protobuf.WellKnownTypes` 名前空間の `Timestamp` クラスと `Duration` クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d305-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="7d305-138">これらのクラスには、`DateTimeOffset`、`DateTime`、および `TimeSpan`との間で変換を行うためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d305-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="7d305-139">`Timestamp` 型は UTC 時刻で動作します。</span><span class="sxs-lookup"><span data-stu-id="7d305-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="7d305-140">`DateTimeOffset` 値は常に0のオフセットを持ち、`DateTime.Kind` プロパティは常に `DateTimeKind.Utc`ます。</span><span class="sxs-lookup"><span data-stu-id="7d305-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="7d305-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="7d305-141">System.Guid</span></span>

<span data-ttu-id="7d305-142">Protobuf は、他のプラットフォームで `UUID` と呼ばれる <xref:System.Guid> の種類を直接サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7d305-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="7d305-143">よく知られている型はありません。</span><span class="sxs-lookup"><span data-stu-id="7d305-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="7d305-144">最良の方法は、標準 `8-4-4-4-12` 16 進数形式 (`45a9fda3-bd01-47a9-8460-c1cd7484b0b3`など) を使用して、`Guid` 値を `string` フィールドとして処理することです。</span><span class="sxs-lookup"><span data-stu-id="7d305-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="7d305-145">すべての言語とプラットフォームで、その形式を解析できます。</span><span class="sxs-lookup"><span data-stu-id="7d305-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="7d305-146">`Guid` 値には、`bytes` フィールドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7d305-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="7d305-147">Protobuf が Java などの他のプラットフォームと対話する場合、*エンディアン*([Wikipedia 定義](https://en.wikipedia.org/wiki/Endianness)) の問題によって動作が不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d305-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="7d305-148">Null 許容型</span><span class="sxs-lookup"><span data-stu-id="7d305-148">Nullable types</span></span>

<span data-ttu-id="7d305-149">のC# Protobuf コード生成では、`int32`の `int` などのネイティブ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d305-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="7d305-150">したがって、値は常に含まれ、null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d305-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="7d305-151">C#コードで `int?` を使用するなど、明示的な null を必要とする値の場合、Protobuf の "既知の型" にはC# 、null 許容型にコンパイルされるラッパーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d305-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="7d305-152">これらを使用するには、次のように `wrappers.proto` を `.proto` ファイルにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7d305-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="7d305-153">Protobuf は、生成されたメッセージプロパティに simple `T?` (`int?`など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d305-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="7d305-154">次の表に、ラッパー型とそれに対応C#する型の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7d305-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="7d305-155">C# 型</span><span class="sxs-lookup"><span data-stu-id="7d305-155">C# type</span></span>   | <span data-ttu-id="7d305-156">既知の型ラッパー</span><span class="sxs-lookup"><span data-stu-id="7d305-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="7d305-157">既知の型 `Timestamp` と `Duration` はクラスとして .NET で表現されるため、null 許容バージョンは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7d305-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="7d305-158">ただし、`DateTimeOffset` または `TimeSpan`に変換する場合は、これらの型のプロパティの null をチェックすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="7d305-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="7d305-159">10 進数</span><span class="sxs-lookup"><span data-stu-id="7d305-159">Decimals</span></span>

<span data-ttu-id="7d305-160">Protobuf は、.NET `decimal` 型をネイティブでサポートしていません。 `double` と `float`だけです。</span><span class="sxs-lookup"><span data-stu-id="7d305-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="7d305-161">Protobuf プロジェクトには、標準 `Decimal` 型を既知の型に追加する可能性についての継続的な議論があり、それをサポートする言語とフレームワークのプラットフォームがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7d305-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="7d305-162">まだ何も実装されていません。</span><span class="sxs-lookup"><span data-stu-id="7d305-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="7d305-163">.NET クライアントとサーバー間の安全なシリアル化に使用できる `decimal` の種類を表すメッセージ定義を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7d305-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="7d305-164">しかし、他のプラットフォームの開発者は、使用されている形式を理解し、独自の処理を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d305-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="7d305-165">Protobuf のカスタム decimal 型の作成</span><span class="sxs-lookup"><span data-stu-id="7d305-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="7d305-166">単純な実装は、一部の Google Api で使用される非標準の `Money` 型に似ていますが、`currency` フィールドはありません。</span><span class="sxs-lookup"><span data-stu-id="7d305-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="7d305-167">`nanos` フィールドは、`0.999_999_999` から `-0.999_999_999`までの値を表します。</span><span class="sxs-lookup"><span data-stu-id="7d305-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="7d305-168">たとえば、`1.5m` `decimal` 値は `{ units = 1, nanos = 500_000_000 }`として表されます。</span><span class="sxs-lookup"><span data-stu-id="7d305-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="7d305-169">この例の `nanos` フィールドでは `sfixed32` 型を使用しているので、より大きな値の場合は `int32` よりも効率的にエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="7d305-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="7d305-170">`units` フィールドが負の値の場合、`nanos` フィールドにも負の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d305-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="7d305-171">`decimal` 値をバイト文字列としてエンコードするためのアルゴリズムは他にもいくつかありますが、このメッセージはどのようなものでも理解しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7d305-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="7d305-172">これらの値は、異なるプラットフォームのエンディアンの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="7d305-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="7d305-173">この型と BCL `decimal` 型の間の変換は、次C#のようにで実装される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d305-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="7d305-174">このようなカスタムメッセージ型を使用する場合は常に、`.proto`のコメントを使用してドキュメントを作成する*必要があり*ます。</span><span class="sxs-lookup"><span data-stu-id="7d305-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="7d305-175">その他の開発者は、独自の言語またはフレームワークで同等の型との間で変換を実装できます。</span><span class="sxs-lookup"><span data-stu-id="7d305-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7d305-176">[前へ](protobuf-messages.md)
>[次へ](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="7d305-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>

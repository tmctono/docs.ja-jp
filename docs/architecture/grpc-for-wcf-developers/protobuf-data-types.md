---
title: Protobuf スカラーデータ型-gRPC (WCF 開発者向け)
description: .NET Core で Protobuf と gRPC がサポートする基本データ型と既知のデータ型について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 5447067b953d257258950d020636e0b38245e20d
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573645"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="3adbd-103">Protobuf スカラー データ型</span><span class="sxs-lookup"><span data-stu-id="3adbd-103">Protobuf scalar data types</span></span>

<span data-ttu-id="3adbd-104">プロトコルバッファー (Protobuf) は、ネイティブスカラー値型の範囲をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3adbd-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="3adbd-105">次の表に、それらすべておよび同等の C# 型の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="3adbd-106">Protobuf 型</span><span class="sxs-lookup"><span data-stu-id="3adbd-106">Protobuf type</span></span> | <span data-ttu-id="3adbd-107">C# 型</span><span class="sxs-lookup"><span data-stu-id="3adbd-107">C# type</span></span>      | <span data-ttu-id="3adbd-108">Notes</span><span class="sxs-lookup"><span data-stu-id="3adbd-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="3adbd-109">1</span><span class="sxs-lookup"><span data-stu-id="3adbd-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="3adbd-110">1</span><span class="sxs-lookup"><span data-stu-id="3adbd-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="3adbd-111">1</span><span class="sxs-lookup"><span data-stu-id="3adbd-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="3adbd-112">1</span><span class="sxs-lookup"><span data-stu-id="3adbd-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="3adbd-113">2</span><span class="sxs-lookup"><span data-stu-id="3adbd-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="3adbd-114">2</span><span class="sxs-lookup"><span data-stu-id="3adbd-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="3adbd-115">2</span><span class="sxs-lookup"><span data-stu-id="3adbd-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="3adbd-116">2</span><span class="sxs-lookup"><span data-stu-id="3adbd-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="3adbd-117">3</span><span class="sxs-lookup"><span data-stu-id="3adbd-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="3adbd-118">4</span><span class="sxs-lookup"><span data-stu-id="3adbd-118">4</span></span>     |

<span data-ttu-id="3adbd-119">メモ:</span><span class="sxs-lookup"><span data-stu-id="3adbd-119">Notes:</span></span>

1. <span data-ttu-id="3adbd-120">との標準エン `int32` コーディング `int64` は、署名された値を操作する場合は非効率的です。</span><span class="sxs-lookup"><span data-stu-id="3adbd-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="3adbd-121">フィールドに負の数値が含まれている可能性がある場合は、 `sint32` 代わりにまたはを使用 `sint64` します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="3adbd-122">これらの型は、それぞれ C# および型にマップさ `int` `long` れます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="3adbd-123">フィールドは、 `fixed` 値がどのようなものであっても、常に同じバイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="3adbd-124">この動作により、シリアル化と逆シリアル化がより大きな値に対して高速化されます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="3adbd-125">Protobuf 文字列は、UTF-8 (または7ビット ASCII) でエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="3adbd-126">エンコードされた長さは 2<sup>32</sup>を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="3adbd-127">Protobuf ランタイムには、 `ByteString` C# の配列との間で簡単にマップできる型が用意されて `byte[]` います。</span><span class="sxs-lookup"><span data-stu-id="3adbd-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="3adbd-128">その他の .NET プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="3adbd-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="3adbd-129">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="3adbd-129">Dates and times</span></span>

<span data-ttu-id="3adbd-130">ネイティブスカラー型は、C# の <xref:System.DateTimeOffset> 、 <xref:System.DateTime> 、およびと等価の日付と時刻の値を提供しません <xref:System.TimeSpan> 。</span><span class="sxs-lookup"><span data-stu-id="3adbd-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="3adbd-131">これらの型は、Google の "既知の型" 拡張機能を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="3adbd-132">これらの拡張機能によって、サポート対象のプラットフォーム全体で複雑なフィールド型に対するコード生成とランタイム サポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="3adbd-133">次の表に日付と時刻の型を示します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="3adbd-134">C# 型</span><span class="sxs-lookup"><span data-stu-id="3adbd-134">C# type</span></span> | <span data-ttu-id="3adbd-135">Protobuf の既知の型</span><span class="sxs-lookup"><span data-stu-id="3adbd-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="3adbd-136">C# クラスで生成されるプロパティは、.NET の日付と時刻の型ではありません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="3adbd-137">このプロパティによって、`Google.Protobuf.WellKnownTypes` 名前空間の `Timestamp` および `Duration` クラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="3adbd-138">これらのクラスには、`DateTimeOffset`、`DateTime`、および `TimeSpan` の間で変換を行うためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3adbd-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="3adbd-139">`Timestamp` 型は UTC 時刻で動作します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="3adbd-140">`DateTimeOffset` 値では常に、オフセットが 0 となり、`DateTime.Kind` プロパティは常に `DateTimeKind.Utc` となります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="3adbd-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="3adbd-141">System.Guid</span></span>

<span data-ttu-id="3adbd-142">Protobuf は、 <xref:System.Guid> `UUID` 他のプラットフォームでと呼ばれる型を直接サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="3adbd-143">よく知られている型はありません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-143">There's no well-known type for it.</span></span>

<span data-ttu-id="3adbd-144">最良の方法は、 `Guid` `string` 標準の `8-4-4-4-12` 16 進形式 (など) を使用して、値をフィールドとして処理することです `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` 。</span><span class="sxs-lookup"><span data-stu-id="3adbd-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="3adbd-145">すべての言語とプラットフォームで、その形式を解析できます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="3adbd-146">値にはフィールドを使用しない `bytes` で `Guid` ください。</span><span class="sxs-lookup"><span data-stu-id="3adbd-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="3adbd-147">Protobuf が Java などの他のプラットフォームと対話する場合、 *エンディアン* ([Wikipedia 定義](https://en.wikipedia.org/wiki/Endianness)) の問題によって動作が不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="3adbd-148">null 許容型</span><span class="sxs-lookup"><span data-stu-id="3adbd-148">Nullable types</span></span>

<span data-ttu-id="3adbd-149">C# に対する Protobuf のコード生成には、ネイティブ型 (`int32` に対して `int` など) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="3adbd-150">したがって、値は常に含まれ、null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="3adbd-151">C# コードでを使用するなど、明示的な null を必要とする値の場合 `int?` 、Protobuf の "既知の型" には、null 許容の C# 型にコンパイルされるラッパーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="3adbd-152">これらのファイルを使用するには、次の `wrappers.proto` ようにファイルにインポートし `.proto` ます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="3adbd-153">Protobuf は、 `T?` 生成されたメッセージプロパティに単純な (たとえば、) を使用し `int?` ます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="3adbd-154">次の表に、ラッパーの型および同等の C# 型の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="3adbd-155">C# 型</span><span class="sxs-lookup"><span data-stu-id="3adbd-155">C# type</span></span>   | <span data-ttu-id="3adbd-156">既知の型のラッパー</span><span class="sxs-lookup"><span data-stu-id="3adbd-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="3adbd-157">既知の型 `Timestamp` とは、 `Duration` .net ではクラスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="3adbd-158">C# 8 以降では、null 値を許容する参照型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="3adbd-159">ただし、またはに変換する場合は、これらの型のプロパティで null をチェックすることが重要です `DateTimeOffset` `TimeSpan` 。</span><span class="sxs-lookup"><span data-stu-id="3adbd-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="3adbd-160">10 進数</span><span class="sxs-lookup"><span data-stu-id="3adbd-160">Decimals</span></span>

<span data-ttu-id="3adbd-161">Protobuf では、.NET の `decimal` 型はネイティブでサポートされません。サポートされるのは、`double` と `float` のみとなります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="3adbd-162">Protobuf プロジェクトでは、標準型を既知の型に追加することが `Decimal` できますが、それをサポートする言語とフレームワークに対応したプラットフォームがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3adbd-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="3adbd-163">まだ何も実装されていません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="3adbd-164">`decimal`.Net クライアントとサーバー間の安全なシリアル化に使用できる型を表すメッセージ定義を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="3adbd-165">しかし、他のプラットフォームの開発者は、使用されている形式を理解し、独自の処理を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="3adbd-166">Protobuf のカスタム 10 進数型の作成</span><span class="sxs-lookup"><span data-stu-id="3adbd-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="3adbd-167">単純な実装は、一部の Google Api で使用される非標準の型に似て `Money` いますが、フィールドはありませ `currency` ん。</span><span class="sxs-lookup"><span data-stu-id="3adbd-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message DecimalValue {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

<span data-ttu-id="3adbd-168">`nanos` フィールドは、`0.999_999_999` から `-0.999_999_999` までの値を表します。</span><span class="sxs-lookup"><span data-stu-id="3adbd-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="3adbd-169">たとえば、`decimal` 値の `1.5m` は `{ units = 1, nanos = 500_000_000 }` として表されます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="3adbd-170">これが、この例の `nanos` フィールドで `sfixed32` 型が使用されている理由です。これで、より大きな値の場合、`int32` よりも効率的にエンコードされるようになります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="3adbd-171">`units` フィールドが負の場合、`nanos` フィールドも負にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="3adbd-172">`decimal` 値をバイト文字列としてエンコードするためのアルゴリズムは他にもいくつかありますが、このメッセージが他のどれよりも理解しやすいものです。</span><span class="sxs-lookup"><span data-stu-id="3adbd-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="3adbd-173">これらの値は、異なるプラットフォームのエンディアンの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="3adbd-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="3adbd-174">この型と BCL の `decimal` 型の間の変換は、このように C# で実装される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3adbd-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

```csharp
namespace CustomTypes
{
    public partial class DecimalValue
    {
        private const decimal NanoFactor = 1_000_000_000;
        public DecimalValue(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.DecimalValue grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.DecimalValue(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.DecimalValue(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="3adbd-175">このようなカスタムメッセージ型を使用する場合は常に、のコメントを使用してドキュメントを作成する *必要があり* `.proto` ます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="3adbd-176">その他の開発者は、独自の言語またはフレームワークで同等の型との間で変換を実装できます。</span><span class="sxs-lookup"><span data-stu-id="3adbd-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3adbd-177">[前へ](protobuf-messages.md)
>[次へ](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="3adbd-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>

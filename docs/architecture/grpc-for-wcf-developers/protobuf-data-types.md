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
# <a name="protobuf-scalar-data-types"></a>Protobuf スカラー データ型

プロトコルバッファー (Protobuf) は、ネイティブスカラー値型の範囲をサポートしています。 次の表に、それらすべておよび同等の C# 型の一覧を示します。

| Protobuf 型 | C# 型      | Notes |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

メモ:

1. との標準エン `int32` コーディング `int64` は、署名された値を操作する場合は非効率的です。 フィールドに負の数値が含まれている可能性がある場合は、 `sint32` 代わりにまたはを使用 `sint64` します。 これらの型は、それぞれ C# および型にマップさ `int` `long` れます。
2. フィールドは、 `fixed` 値がどのようなものであっても、常に同じバイト数を使用します。 この動作により、シリアル化と逆シリアル化がより大きな値に対して高速化されます。
3. Protobuf 文字列は、UTF-8 (または7ビット ASCII) でエンコードされます。 エンコードされた長さは 2<sup>32</sup>を超えることはできません。
4. Protobuf ランタイムには、 `ByteString` C# の配列との間で簡単にマップできる型が用意されて `byte[]` います。

## <a name="other-net-primitive-types"></a>その他の .NET プリミティブ型

### <a name="dates-and-times"></a>日付と時刻

ネイティブスカラー型は、C# の <xref:System.DateTimeOffset> 、 <xref:System.DateTime> 、およびと等価の日付と時刻の値を提供しません <xref:System.TimeSpan> 。 これらの型は、Google の "既知の型" 拡張機能を使用して指定できます。 これらの拡張機能によって、サポート対象のプラットフォーム全体で複雑なフィールド型に対するコード生成とランタイム サポートが提供されます。

次の表に日付と時刻の型を示します。

| C# 型 | Protobuf の既知の型 |
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

C# クラスで生成されるプロパティは、.NET の日付と時刻の型ではありません。 このプロパティによって、`Google.Protobuf.WellKnownTypes` 名前空間の `Timestamp` および `Duration` クラスが使用されます。 これらのクラスには、`DateTimeOffset`、`DateTime`、および `TimeSpan` の間で変換を行うためのメソッドが用意されています。

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
> `Timestamp` 型は UTC 時刻で動作します。 `DateTimeOffset` 値では常に、オフセットが 0 となり、`DateTime.Kind` プロパティは常に `DateTimeKind.Utc` となります。

### <a name="systemguid"></a>System.Guid

Protobuf は、 <xref:System.Guid> `UUID` 他のプラットフォームでと呼ばれる型を直接サポートしていません。 よく知られている型はありません。

最良の方法は、 `Guid` `string` 標準の `8-4-4-4-12` 16 進形式 (など) を使用して、値をフィールドとして処理することです `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` 。 すべての言語とプラットフォームで、その形式を解析できます。

値にはフィールドを使用しない `bytes` で `Guid` ください。 Protobuf が Java などの他のプラットフォームと対話する場合、 *エンディアン* ([Wikipedia 定義](https://en.wikipedia.org/wiki/Endianness)) の問題によって動作が不安定になる可能性があります。

### <a name="nullable-types"></a>null 許容型

C# に対する Protobuf のコード生成には、ネイティブ型 (`int32` に対して `int` など) が使用されます。 したがって、値は常に含まれ、null にすることはできません。

C# コードでを使用するなど、明示的な null を必要とする値の場合 `int?` 、Protobuf の "既知の型" には、null 許容の C# 型にコンパイルされるラッパーが含まれます。 これらのファイルを使用するには、次の `wrappers.proto` ようにファイルにインポートし `.proto` ます。

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf は、 `T?` 生成されたメッセージプロパティに単純な (たとえば、) を使用し `int?` ます。

次の表に、ラッパーの型および同等の C# 型の完全な一覧を示します。

| C# 型   | 既知の型のラッパー       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

既知の型 `Timestamp` とは、 `Duration` .net ではクラスとして表されます。 C# 8 以降では、null 値を許容する参照型を使用できます。 ただし、またはに変換する場合は、これらの型のプロパティで null をチェックすることが重要です `DateTimeOffset` `TimeSpan` 。

## <a name="decimals"></a>10 進数

Protobuf では、.NET の `decimal` 型はネイティブでサポートされません。サポートされるのは、`double` と `float` のみとなります。 Protobuf プロジェクトでは、標準型を既知の型に追加することが `Decimal` できますが、それをサポートする言語とフレームワークに対応したプラットフォームがサポートされています。 まだ何も実装されていません。

`decimal`.Net クライアントとサーバー間の安全なシリアル化に使用できる型を表すメッセージ定義を作成することができます。 しかし、他のプラットフォームの開発者は、使用されている形式を理解し、独自の処理を実装する必要があります。

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Protobuf のカスタム 10 進数型の作成

単純な実装は、一部の Google Api で使用される非標準の型に似て `Money` いますが、フィールドはありませ `currency` ん。

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

`nanos` フィールドは、`0.999_999_999` から `-0.999_999_999` までの値を表します。 たとえば、`decimal` 値の `1.5m` は `{ units = 1, nanos = 500_000_000 }` として表されます。 これが、この例の `nanos` フィールドで `sfixed32` 型が使用されている理由です。これで、より大きな値の場合、`int32` よりも効率的にエンコードされるようになります。 `units` フィールドが負の場合、`nanos` フィールドも負にする必要があります。

> [!NOTE]
> `decimal` 値をバイト文字列としてエンコードするためのアルゴリズムは他にもいくつかありますが、このメッセージが他のどれよりも理解しやすいものです。 これらの値は、異なるプラットフォームのエンディアンの影響を受けません。

この型と BCL の `decimal` 型の間の変換は、このように C# で実装される場合があります。

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
> このようなカスタムメッセージ型を使用する場合は常に、のコメントを使用してドキュメントを作成する *必要があり* `.proto` ます。 その他の開発者は、独自の言語またはフレームワークで同等の型との間で変換を実装できます。

>[!div class="step-by-step"]
>[前へ](protobuf-messages.md)
>[次へ](protobuf-nested-types.md)

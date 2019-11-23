---
title: Protobuf variant 型のフィールドと、WCF 開発者向け gRPC の組み合わせ
description: Any 型および Oneof キーワードを使用して、メッセージ内のバリアントオブジェクト型を表す方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971617"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="839fe-103">Protobuf variant 型のフィールドをすべて使用します。</span><span class="sxs-lookup"><span data-stu-id="839fe-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="839fe-104">WCF での動的プロパティ型 (`object`型のプロパティ) の処理は複雑です。</span><span class="sxs-lookup"><span data-stu-id="839fe-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="839fe-105">シリアライザーを指定する必要があります。また、 [Knowntype](xref:System.Runtime.Serialization.KnownTypeAttribute)属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="839fe-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="839fe-106">Protobuf には、複数の型の値を処理するための2つの簡単なオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="839fe-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="839fe-107">`Any` 型は既知の Protobuf メッセージ型を表すことができますが、`oneof` キーワードを使用すると、特定のメッセージで設定できるフィールドの範囲が1つだけであることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="839fe-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="839fe-108">任意</span><span class="sxs-lookup"><span data-stu-id="839fe-108">Any</span></span>

<span data-ttu-id="839fe-109">`Any` は、Protobuf の "既知の型" の1つです。サポートされているすべての言語の実装で、便利で再利用可能なメッセージ型のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="839fe-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="839fe-110">`Any` の種類を使用するには、`google/protobuf/any.proto` 定義をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="839fe-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

<span data-ttu-id="839fe-111">C#コードでは、`Any` クラスに、フィールドの設定、メッセージの抽出、および型のチェックを行うメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="839fe-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="839fe-112">生成された各型の `Descriptor` 静的フィールドは、`Any` フィールド型を解決するために Protobuf の内部リフレクションコードによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="839fe-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="839fe-113">`TryUnpack<T>` メソッドもありますが、`T` の初期化されていないインスタンスは失敗した場合でも作成されるため、上記のように `Is` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="839fe-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="839fe-114">うち</span><span class="sxs-lookup"><span data-stu-id="839fe-114">Oneof</span></span>

<span data-ttu-id="839fe-115">Oneof フィールドは言語機能です。 `oneof` キーワードは、メッセージクラスを生成するときにコンパイラによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="839fe-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="839fe-116">`oneof` を使用して `ChangeNotification` メッセージを指定する場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="839fe-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

<span data-ttu-id="839fe-117">`oneof` セット内のフィールドは、メッセージの宣言全体で一意のフィールド番号を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="839fe-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="839fe-118">`oneof`を使用すると、生成C#されるコードには、どのフィールドが設定されているかを指定する列挙が含まれます。</span><span class="sxs-lookup"><span data-stu-id="839fe-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="839fe-119">列挙をテストして、どのフィールドが設定されているかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="839fe-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="839fe-120">設定されていないフィールドは、例外をスローするのではなく、`null` または既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="839fe-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="839fe-121">`oneof` セットの一部であるフィールドを設定すると、セット内の他のすべてのフィールドが自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="839fe-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="839fe-122">`oneof`で `repeated` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="839fe-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="839fe-123">代わりに、この制限を回避するために、繰り返しフィールドまたは `oneof` 設定を使用して、入れ子になったメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="839fe-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="839fe-124">[前へ](protobuf-reserved.md)
>[次へ](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="839fe-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>

---
title: Protobuf variant 型のフィールドと、WCF 開発者向け gRPC の組み合わせ
description: Any 型および Oneof キーワードを使用して、メッセージ内のバリアントオブジェクト型を表す方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543197"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="3dc9d-103">Protobuf variant 型のフィールドをすべて使用します。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="3dc9d-104">Windows Communication Foundation (WCF) での動的プロパティ型 (`object`型のプロパティ) の処理は複雑になります。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="3dc9d-105">たとえば、シリアライザーを指定し、 [Knowntype](xref:System.Runtime.Serialization.KnownTypeAttribute)属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="3dc9d-106">プロトコルバッファー (Protobuf) には、複数の型の値を処理するための2つの簡単なオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="3dc9d-107">`Any` 型は、既知の Protobuf メッセージ型を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="3dc9d-108">また、`oneof` キーワードを使用して、任意のメッセージで設定できるフィールドの範囲が1つだけであることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="3dc9d-109">Any</span><span class="sxs-lookup"><span data-stu-id="3dc9d-109">Any</span></span>

<span data-ttu-id="3dc9d-110">`Any` は、Protobuf の "既知の型" の1つです。サポートされているすべての言語の実装で、便利で再利用可能なメッセージ型のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="3dc9d-111">`Any` の種類を使用するには、`google/protobuf/any.proto` 定義をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="3dc9d-112">C#コードでは、`Any` クラスに、フィールドの設定、メッセージの抽出、および型のチェックを行うメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="3dc9d-113">Protobuf の内部リフレクションコードでは、生成された各型の `Descriptor` 静的フィールドを使用して `Any` フィールド型を解決します。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="3dc9d-114">`TryUnpack<T>` メソッドもありますが、`T` の初期化されていないインスタンスは失敗した場合でも作成されます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="3dc9d-115">前述のように `Is` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="3dc9d-116">うち</span><span class="sxs-lookup"><span data-stu-id="3dc9d-116">Oneof</span></span>

<span data-ttu-id="3dc9d-117">Oneof フィールドは言語機能です。コンパイラは、message クラスを生成するときに、`oneof` キーワードを処理します。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="3dc9d-118">`oneof` を使用して `ChangeNotification` メッセージを指定する場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="3dc9d-119">`oneof` セット内のフィールドには、メッセージの宣言全体で一意のフィールド番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="3dc9d-120">`oneof`を使用すると、生成C#されるコードには、どのフィールドが設定されているかを指定する列挙が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="3dc9d-121">列挙をテストして、どのフィールドが設定されているかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="3dc9d-122">設定されていないフィールドは、例外をスローするのではなく、`null` または既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="3dc9d-123">`oneof` セットの一部であるフィールドを設定すると、セット内の他のすべてのフィールドが自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="3dc9d-124">`oneof`で `repeated` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="3dc9d-125">代わりに、この制限を回避するために、繰り返しフィールドまたは `oneof` 設定を使用して、入れ子になったメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3dc9d-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3dc9d-126">[前へ](protobuf-reserved.md)
>[次へ](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="3dc9d-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>

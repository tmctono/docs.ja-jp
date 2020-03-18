---
title: プロトブーフ メッセージ - WCF 開発者向け gRPC
description: プロトブーフ メッセージが IDL で定義され、C# で生成される方法について説明します。
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147985"
---
# <a name="protobuf-messages"></a><span data-ttu-id="1069f-103">Protobuf メッセージ</span><span class="sxs-lookup"><span data-stu-id="1069f-103">Protobuf messages</span></span>

<span data-ttu-id="1069f-104">このセクションでは、プロトコル バッファー (Protobuf) メッセージ`.proto`をファイルで宣言する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1069f-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="1069f-105">フィールドの数値と型の基本的な概念について説明し、コンパイラが生成する C#`protoc`コードを調べています。</span><span class="sxs-lookup"><span data-stu-id="1069f-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="1069f-106">この章の残りの部分では、Protobuf でのデータの種類の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="1069f-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="1069f-107">メッセージの宣言</span><span class="sxs-lookup"><span data-stu-id="1069f-107">Declaring a message</span></span>

<span data-ttu-id="1069f-108">Windows コミュニケーション ファウンデーション`Stock`(WCF) では、株式市場取引アプリケーションのクラスは、次の例のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="1069f-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

<span data-ttu-id="1069f-109">Protobuf で同等のクラスを実装するには、ファイル内で宣言`.proto`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1069f-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="1069f-110">コンパイラ`protoc`は、ビルド プロセスの一部として .NET クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="1069f-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

<span data-ttu-id="1069f-111">最初の行は、使用されている構文バージョンを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1069f-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="1069f-112">バージョン3の言語は2016年にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="1069f-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="1069f-113">gRPC サービスに推奨されるバージョンです。</span><span class="sxs-lookup"><span data-stu-id="1069f-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="1069f-114">この`option csharp_namespace`行は、生成された C# 型に使用される名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="1069f-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="1069f-115">このオプションは、ファイルが他の`.proto`言語用にコンパイルされる場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1069f-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="1069f-116">Protobuf ファイルには、多くの場合、複数の言語の言語固有のオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1069f-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="1069f-117">メッセージ`Stock`定義は、4 つのフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="1069f-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="1069f-118">それぞれにタイプ、名前、およびフィールド番号があります。</span><span class="sxs-lookup"><span data-stu-id="1069f-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="1069f-119">フィールド番号</span><span class="sxs-lookup"><span data-stu-id="1069f-119">Field numbers</span></span>

<span data-ttu-id="1069f-120">フィールド番号はプロトブーフの重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="1069f-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="1069f-121">バイナリエンコードデータのフィールドを識別するために使用されるため、サービスのバージョン間で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1069f-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="1069f-122">利点は、下位互換性と上位互換性が可能です。</span><span class="sxs-lookup"><span data-stu-id="1069f-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="1069f-123">クライアントとサービスは、欠損値の可能性が処理される限り、知らないフィールド番号を無視します。</span><span class="sxs-lookup"><span data-stu-id="1069f-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="1069f-124">バイナリ形式では、フィールド番号は型識別子と組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="1069f-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="1069f-125">1 から 15 までのフィールド番号は、その型を 1 バイトとしてエンコードできます。</span><span class="sxs-lookup"><span data-stu-id="1069f-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="1069f-126">16 から 2,047 までの数値は 2 バイトです。</span><span class="sxs-lookup"><span data-stu-id="1069f-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="1069f-127">メッセージに何らかの理由で 2,047 を超えるフィールドが必要な場合は、高く設定できます。</span><span class="sxs-lookup"><span data-stu-id="1069f-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="1069f-128">フィールド番号 1 から 15 の単一バイト ID はパフォーマンスが向上するため、最も基本的で頻繁に使用されるフィールドに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1069f-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="1069f-129">型</span><span class="sxs-lookup"><span data-stu-id="1069f-129">Types</span></span>

<span data-ttu-id="1069f-130">型宣言では、Protobuf のネイティブ スカラー データ型を使用[します](protobuf-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="1069f-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="1069f-131">この章の残りの部分では、Protobuf の組み込み型について説明し、一般的な .NET 型との関係を示します。</span><span class="sxs-lookup"><span data-stu-id="1069f-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="1069f-132">Protobuf は型を`decimal`ネイティブにサポートしないので`double`、代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1069f-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="1069f-133">完全な 10 進精度を必要とするアプリケーションについては、この章の次の[部分の小数点以下のセクション](protobuf-data-types.md#decimals)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1069f-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="1069f-134">生成されたコード</span><span class="sxs-lookup"><span data-stu-id="1069f-134">The generated code</span></span>

<span data-ttu-id="1069f-135">アプリケーションをビルドすると、Protobuf は各メッセージのクラスを作成し、ネイティブ型を C# 型にマップします。</span><span class="sxs-lookup"><span data-stu-id="1069f-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="1069f-136">生成された`Stock`型には、次のシグネチャが付けられます。</span><span class="sxs-lookup"><span data-stu-id="1069f-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="1069f-137">実際に生成されるコードはこれよりはるかに複雑です。</span><span class="sxs-lookup"><span data-stu-id="1069f-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="1069f-138">その理由は、各クラスに、自身をシリアル化し、バイナリ ワイヤ形式に逆シリアル化するために必要なすべてのコードが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="1069f-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="1069f-139">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="1069f-139">Property names</span></span>

<span data-ttu-id="1069f-140">Protobuf コンパイラは、ファイル`PascalCase`に含まれている`snake_case`が、プロパティ名に適用されることに`.proto`注意してください。</span><span class="sxs-lookup"><span data-stu-id="1069f-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="1069f-141">[Protobuf スタイル ガイド](https://developers.google.com/protocol-buffers/docs/style)では、`snake_case`他のプラットフォームのコード生成によって、その規則に対して期待される大文字と小文字が生成されるように、メッセージ定義で使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1069f-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1069f-142">[前次](protocol-buffers.md)
>[Next](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="1069f-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>

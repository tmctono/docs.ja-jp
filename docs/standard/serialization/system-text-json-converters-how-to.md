---
title: JSON シリアル化のカスタムコンバーターを記述する方法-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: f72d2d83d701b20648140900d65c9098a8abb721
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164061"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="638c3-102">.NET で JSON シリアル化 (マーシャリング) のカスタムコンバーターを記述する方法</span><span class="sxs-lookup"><span data-stu-id="638c3-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="638c3-103">この記事では、<xref:System.Text.Json> 名前空間に用意されている JSON シリアル化クラスのカスタムコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="638c3-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="638c3-104">`System.Text.Json`の概要については、「 [.net で JSON をシリアル化および逆シリアル化する方法](system-text-json-how-to.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="638c3-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="638c3-105">*コンバーター*は、オブジェクトまたは値を JSON との間で変換するクラスです。</span><span class="sxs-lookup"><span data-stu-id="638c3-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="638c3-106">`System.Text.Json` 名前空間には、JavaScript プリミティブにマップされるほとんどのプリミティブ型用の組み込みのコンバーターがあります。</span><span class="sxs-lookup"><span data-stu-id="638c3-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="638c3-107">カスタムコンバーターは、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="638c3-107">You can write custom converters:</span></span>

* <span data-ttu-id="638c3-108">組み込みのコンバーターの既定の動作をオーバーライドする場合は。</span><span class="sxs-lookup"><span data-stu-id="638c3-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="638c3-109">たとえば、既定の ISO 8601-1:2019 形式ではなく、`DateTime` 値を mm/dd/yyyy 形式で表すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="638c3-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="638c3-110">カスタム値型をサポートする場合は。</span><span class="sxs-lookup"><span data-stu-id="638c3-110">To support a custom value type.</span></span> <span data-ttu-id="638c3-111">たとえば、`PhoneNumber` 構造体などです。</span><span class="sxs-lookup"><span data-stu-id="638c3-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="638c3-112">また、カスタムコンバーターを作成して、現在のリリースに含まれていない機能を使用して `System.Text.Json` をカスタマイズまたは拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="638c3-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="638c3-113">この記事の後半では、次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="638c3-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="638c3-114">推論された[型をオブジェクトのプロパティに逆シリアル](#deserialize-inferred-types-to-object-properties)化します。</span><span class="sxs-lookup"><span data-stu-id="638c3-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="638c3-115">[文字列以外のキーを使用した辞書をサポート](#support-dictionary-with-non-string-key)します。</span><span class="sxs-lookup"><span data-stu-id="638c3-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="638c3-116">[ポリモーフィック逆シリアル化をサポート](#support-polymorphic-deserialization)します。</span><span class="sxs-lookup"><span data-stu-id="638c3-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="638c3-117">カスタムコンバーターパターン</span><span class="sxs-lookup"><span data-stu-id="638c3-117">Custom converter patterns</span></span>

<span data-ttu-id="638c3-118">カスタムコンバーターを作成するには、基本パターンとファクトリパターンという2つのパターンがあります。</span><span class="sxs-lookup"><span data-stu-id="638c3-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="638c3-119">ファクトリパターンは、型 `Enum` またはオープンジェネリックを処理するコンバーター用です。</span><span class="sxs-lookup"><span data-stu-id="638c3-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="638c3-120">基本パターンは、非ジェネリックおよびクローズジェネリック型用です。</span><span class="sxs-lookup"><span data-stu-id="638c3-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="638c3-121">たとえば、次の型のコンバーターには、ファクトリパターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="638c3-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="638c3-122">基本的なパターンによって処理できる型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="638c3-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="638c3-123">基本パターンでは、1つの型を処理できるクラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="638c3-124">ファクトリパターンは、実行時に特定の型が必要であることを判断し、適切なコンバーターを動的に作成するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="638c3-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="638c3-125">基本的なコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="638c3-125">Sample basic converter</span></span>

<span data-ttu-id="638c3-126">次のサンプルは、既存のデータ型の既定のシリアル化をオーバーライドするコンバーターです。</span><span class="sxs-lookup"><span data-stu-id="638c3-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="638c3-127">コンバーターでは、`DateTimeOffset` プロパティに mm/dd/yyyy 形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="638c3-128">サンプルファクトリパターンコンバーター</span><span class="sxs-lookup"><span data-stu-id="638c3-128">Sample factory pattern converter</span></span>

<span data-ttu-id="638c3-129">次のコードは、`Dictionary<Enum,TValue>`で動作するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="638c3-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="638c3-130">このコードは、最初のジェネリック型パラメーターが `Enum`、2番目のジェネリック型パラメーターが開いているため、ファクトリパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="638c3-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="638c3-131">`CanConvert` メソッドは、2つのジェネリックパラメーターを持つ `Dictionary` に対してのみ `true` を返します。最初のパラメーターは `Enum` 型です。</span><span class="sxs-lookup"><span data-stu-id="638c3-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="638c3-132">内部コンバーターは、`TValue`に対して実行時に提供されるいずれかの型を処理する既存のコンバーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="638c3-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="638c3-133">上記のコードは、この記事の後半で説明する[文字列以外のキーを使用したサポート辞書](#support-dictionary-with-non-string-key)に示されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="638c3-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="638c3-134">基本的なパターンに従う手順</span><span class="sxs-lookup"><span data-stu-id="638c3-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="638c3-135">次の手順では、基本的なパターンに従ってコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="638c3-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="638c3-136">`T` がシリアル化および逆シリアル化される型である <xref:System.Text.Json.Serialization.JsonConverter%601> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="638c3-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="638c3-137">`Read` メソッドをオーバーライドして受信 JSON を逆シリアル化し、型 `T`に変換します。</span><span class="sxs-lookup"><span data-stu-id="638c3-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="638c3-138">メソッドに渡された <xref:System.Text.Json.Utf8JsonReader> を使用して、JSON を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="638c3-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="638c3-139">`Write` メソッドをオーバーライドして、`T`型の受信オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="638c3-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="638c3-140">メソッドに渡された <xref:System.Text.Json.Utf8JsonWriter> を使用して JSON を記述します。</span><span class="sxs-lookup"><span data-stu-id="638c3-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="638c3-141">`CanConvert` メソッドは、必要な場合にのみオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="638c3-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="638c3-142">変換する型が `T`型である場合、既定の実装は `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="638c3-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="638c3-143">したがって、型 `T` だけをサポートするコンバーターは、このメソッドをオーバーライドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="638c3-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="638c3-144">このメソッドをオーバーライドする必要があるコンバーターの例については、この記事で後述する「[ポリモーフィックな逆シリアル化](#support-polymorphic-deserialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="638c3-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="638c3-145">[組み込みのコンバーターソースコード](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/)は、カスタムコンバーターを作成するための参照の実装として参照できます。</span><span class="sxs-lookup"><span data-stu-id="638c3-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="638c3-146">ファクトリパターンに従う手順</span><span class="sxs-lookup"><span data-stu-id="638c3-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="638c3-147">次の手順では、ファクトリパターンに従ってコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="638c3-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="638c3-148"><xref:System.Text.Json.Serialization.JsonConverterFactory> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="638c3-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="638c3-149">変換する型が、コンバーターが処理できる型である場合に true を返すように `CanConvert` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="638c3-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="638c3-150">たとえば、コンバーターが `List<T>` 用の場合、`List<int>`、`List<string>`、および `List<DateTime>`だけを処理できます。</span><span class="sxs-lookup"><span data-stu-id="638c3-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="638c3-151">`CreateConverter` メソッドをオーバーライドして、実行時に提供される変換の種類を処理するコンバータークラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="638c3-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="638c3-152">`CreateConverter` メソッドによってインスタンス化されるコンバータークラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="638c3-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="638c3-153">オブジェクトを文字列との間で変換するコードはすべての型で同じではないため、オープンジェネリックにはファクトリパターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="638c3-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="638c3-154">オープンジェネリック型 (`List<T>`など) のコンバーターは、背後にあるクローズジェネリック型 (`List<DateTime>`など) のコンバーターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="638c3-155">コードは、コンバーターが処理できる各閉じられたジェネリック型を処理するように記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="638c3-156">`Enum` 型はオープンジェネリック型に似ています。 `Enum` のコンバーターは、シーンの背後にある特定の `Enum` (`WeekdaysEnum`など) のコンバーターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="638c3-157">エラー処理</span><span class="sxs-lookup"><span data-stu-id="638c3-157">Error handling</span></span>

<span data-ttu-id="638c3-158">エラー処理コードで例外をスローする必要がある場合は、メッセージを使用せずに <xref:System.Text.Json.JsonException> をスローすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="638c3-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="638c3-159">この例外の種類では、エラーの原因となった JSON の部分へのパスを含むメッセージが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="638c3-160">たとえば、ステートメント `throw new JsonException();` では、次の例のようなエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="638c3-161">メッセージ (`throw new JsonException("Error occurred")`など) を指定した場合でも、例外は <xref:System.Text.Json.JsonException.Path> プロパティのパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="638c3-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="638c3-162">カスタムコンバーターを登録する</span><span class="sxs-lookup"><span data-stu-id="638c3-162">Register a custom converter</span></span>

<span data-ttu-id="638c3-163">カスタムコンバーターを*登録*して、`Serialize` および `Deserialize` メソッドで使用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="638c3-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="638c3-164">次のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="638c3-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="638c3-165">コンバータークラスのインスタンスを <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="638c3-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="638c3-166">カスタムコンバーターを必要とするプロパティに[[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="638c3-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="638c3-167">[[Jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)属性をカスタム値型を表すクラスまたは構造体に適用します。</span><span class="sxs-lookup"><span data-stu-id="638c3-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="638c3-168">登録サンプル-コンバーターコレクション</span><span class="sxs-lookup"><span data-stu-id="638c3-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="638c3-169"><xref:System.DateTimeOffset>型のプロパティの既定値 <xref:System.ComponentModel.DateTimeOffsetConverter> する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="638c3-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="638c3-170">次の型のインスタンスをシリアル化するとします。</span><span class="sxs-lookup"><span data-stu-id="638c3-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="638c3-171">カスタムコンバーターが使用されたことを示す JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="638c3-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="638c3-172">次のコードでは、カスタム `DateTimeOffset` コンバーターを使用して逆シリアル化するのと同じアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="638c3-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="638c3-173">登録のサンプル-[JsonConverter] プロパティ</span><span class="sxs-lookup"><span data-stu-id="638c3-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="638c3-174">次のコードでは、`Date` プロパティのカスタムコンバーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="638c3-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="638c3-175">`WeatherForecastWithConverterAttribute` をシリアル化するコードでは、`JsonSerializeOptions.Converters`を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="638c3-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="638c3-176">逆シリアル化するコードでは、`Converters`を使用する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="638c3-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="638c3-177">登録サンプル-[JsonConverter] 型</span><span class="sxs-lookup"><span data-stu-id="638c3-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="638c3-178">次に、構造体を作成し、それに `[JsonConverter]` 属性を適用するコードを示します。</span><span class="sxs-lookup"><span data-stu-id="638c3-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="638c3-179">前の構造体のカスタムコンバーターは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="638c3-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="638c3-180">構造体の `[JsonConvert]` 属性は、`Temperature`型のプロパティの既定値としてカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="638c3-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="638c3-181">コンバーターは、シリアル化または逆シリアル化するときに、次の型の `TemperatureCelsius` プロパティで自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="638c3-182">コンバーターの登録の優先順位</span><span class="sxs-lookup"><span data-stu-id="638c3-182">Converter registration precedence</span></span>

<span data-ttu-id="638c3-183">シリアル化または逆シリアル化の際には、次の順序で JSON 要素ごとにコンバーターが選択され、最も高い優先度から順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="638c3-184">`[JsonConverter]` プロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="638c3-185">`Converters` コレクションに追加されたコンバーター。</span><span class="sxs-lookup"><span data-stu-id="638c3-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="638c3-186">`[JsonConverter]` カスタム値型または POCO に適用されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="638c3-187">1つの型に対して複数のカスタムコンバーターが `Converters` コレクションに登録されている場合、`CanConvert` に対して true を返す最初のコンバーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="638c3-188">組み込みのコンバーターは、適用可能なカスタムコンバーターが登録されていない場合にのみ選択されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="638c3-189">一般的なシナリオのコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="638c3-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="638c3-190">以下のセクションでは、組み込み機能で処理されない一般的なシナリオに対処するコンバーターのサンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="638c3-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="638c3-191">推論された型のオブジェクトプロパティへの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="638c3-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="638c3-192">文字列以外のキーを使用したサポート辞書</span><span class="sxs-lookup"><span data-stu-id="638c3-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="638c3-193">ポリモーフィック逆シリアル化のサポート</span><span class="sxs-lookup"><span data-stu-id="638c3-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="638c3-194">推論された型のオブジェクトプロパティへの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="638c3-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="638c3-195">`object`型のプロパティに逆シリアル化すると、`JsonElement` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="638c3-196">その理由は、デシリアライザーは、作成する CLR 型を認識しないため、推測しようとしません。</span><span class="sxs-lookup"><span data-stu-id="638c3-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="638c3-197">たとえば、JSON プロパティに "true" が含まれている場合、デシリアライザーは、値が `Boolean`であることを推論しません。また、要素に "01/01/2019" がある場合、デシリアライザーは `DateTime`であることを推論しません。</span><span class="sxs-lookup"><span data-stu-id="638c3-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="638c3-198">型の推定は不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="638c3-199">デシリアライザーが、小数点のない JSON 番号を `long`として解析する場合、値が最初に `ulong` または `BigInteger`としてシリアル化された場合、範囲外の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="638c3-200">数値が最初に `decimal`としてシリアル化された場合、`double` として小数点がある数値を解析すると、精度が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="638c3-201">型の推定が必要なシナリオでは、次のコードは `object` プロパティのカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="638c3-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="638c3-202">コードは次のように変換します。</span><span class="sxs-lookup"><span data-stu-id="638c3-202">The code converts:</span></span>

* <span data-ttu-id="638c3-203">`true` と `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="638c3-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="638c3-204">`long` に10進数を含まない数値</span><span class="sxs-lookup"><span data-stu-id="638c3-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="638c3-205">`double` に10進数が含まれる数値</span><span class="sxs-lookup"><span data-stu-id="638c3-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="638c3-206">`DateTime` する日付</span><span class="sxs-lookup"><span data-stu-id="638c3-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="638c3-207">`string` する文字列</span><span class="sxs-lookup"><span data-stu-id="638c3-207">Strings to `string`</span></span>
* <span data-ttu-id="638c3-208">他のすべての `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="638c3-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="638c3-209">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="638c3-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="638c3-210">`object` プロパティを持つ型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="638c3-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="638c3-211">次の JSON の例には、`DateTime`、`long`、および `string`として逆シリアル化される値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="638c3-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="638c3-212">カスタムコンバーターを使用しない場合、逆シリアル化によって各プロパティに `JsonElement` が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="638c3-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="638c3-213">`System.Text.Json.Serialization` 名前空間の[単体テストフォルダー](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)には、`object` プロパティへの逆シリアル化を処理するカスタムコンバーターの例が多数あります。</span><span class="sxs-lookup"><span data-stu-id="638c3-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="638c3-214">文字列以外のキーを使用したサポート辞書</span><span class="sxs-lookup"><span data-stu-id="638c3-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="638c3-215">ディクショナリコレクションの組み込みサポートは `Dictionary<string, TValue>`用です。</span><span class="sxs-lookup"><span data-stu-id="638c3-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="638c3-216">つまり、キーは文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-216">That is, the key must be a string.</span></span> <span data-ttu-id="638c3-217">キーとして整数またはその他の型を持つディクショナリをサポートするには、カスタムコンバーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="638c3-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="638c3-218">次のコードは、`Dictionary<Enum,TValue>`で動作するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="638c3-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="638c3-219">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="638c3-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="638c3-220">コンバーターは、次の `Enum`を使用する次のクラスの `TemperatureRanges` プロパティをシリアル化および逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="638c3-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="638c3-221">シリアル化からの JSON 出力は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="638c3-221">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="638c3-222">`System.Text.Json.Serialization` 名前空間の[単体テストフォルダー](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)には、文字列キー以外のディクショナリを処理するカスタムコンバーターの例が多数あります。</span><span class="sxs-lookup"><span data-stu-id="638c3-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="638c3-223">ポリモーフィック逆シリアル化のサポート</span><span class="sxs-lookup"><span data-stu-id="638c3-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="638c3-224">組み込み機能は、[ポリモーフィックなシリアル化](system-text-json-how-to.md#serialize-properties-of-derived-classes)の範囲を制限しますが、逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="638c3-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="638c3-225">逆シリアル化を行うには、カスタムコンバーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="638c3-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="638c3-226">たとえば、`Person` 抽象基本クラスがあり、`Employee` および `Customer` 派生クラスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="638c3-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="638c3-227">ポリモーフィックな逆シリアル化とは、デザイン時に `Person` を逆シリアル化ターゲットとして指定できること、および JSON 内の `Customer` オブジェクトと `Employee` オブジェクトが実行時に正しく逆シリアル化されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="638c3-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="638c3-228">逆シリアル化中に、JSON で必要な型を識別する手掛かりを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="638c3-229">使用できる手掛かりの種類は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="638c3-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="638c3-230">たとえば、識別子のプロパティを使用できる場合や、特定のプロパティの有無に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="638c3-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="638c3-231">`System.Text.Json` の現在のリリースでは、ポリモーフィックな逆シリアル化のシナリオを処理する方法を指定する属性が提供されないため、カスタムコンバーターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="638c3-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="638c3-232">次のコードは、基底クラス、2つの派生クラス、およびそれらのカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="638c3-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="638c3-233">コンバーターは、ポリモーフィックな逆シリアル化を行うために識別子プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="638c3-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="638c3-234">型識別子はクラス定義に含まれていませんが、シリアル化中に作成され、逆シリアル化中に読み取られます。</span><span class="sxs-lookup"><span data-stu-id="638c3-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="638c3-235">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="638c3-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="638c3-236">コンバーターは、同じコンバーターを使用して作成された JSON を逆シリアル化できます。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="638c3-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

<span data-ttu-id="638c3-237">前の例のコンバーターコードは、各プロパティを手動で読み取り、書き込みます。</span><span class="sxs-lookup"><span data-stu-id="638c3-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="638c3-238">別の方法として、`Deserialize` または `Serialize` を呼び出して、一部の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="638c3-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="638c3-239">例については、[この StackOverflow の投稿](https://stackoverflow.com/a/59744873/12509023)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="638c3-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="638c3-240">その他のカスタムコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="638c3-240">Other custom converter samples</span></span>

<span data-ttu-id="638c3-241">[Newtonsoft.Json から System.Text.Jsonへの移行に](system-text-json-migrate-from-newtonsoft-how-to.md)関する記事には、カスタムコンバーターの追加のサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="638c3-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="638c3-242">`System.Text.Json.Serialization` ソースコードの[単体テストフォルダー](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)には、次のような他のカスタムコンバーターのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="638c3-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="638c3-243">[逆シリアル化時に null を0に変換する Int32 コンバーター](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="638c3-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="638c3-244">[逆シリアル化時に文字列と数値の両方を使用できる Int32 コンバーター](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="638c3-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="638c3-245">[列挙型コンバーター](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="638c3-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="638c3-246">[外部データを受け入れる\<T > コンバーターの一覧表示](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="638c3-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="638c3-247">[コンマで区切られた数値のリストを処理する Long [] コンバーター](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="638c3-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span> 

<span data-ttu-id="638c3-248">既存の組み込みコンバーターの動作を変更するコンバーターを作成する必要がある場合は、[既存のコンバーターのソースコード](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)を取得して、カスタマイズの開始点として機能させることができます。</span><span class="sxs-lookup"><span data-stu-id="638c3-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="638c3-249">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="638c3-249">Additional resources</span></span>

* <span data-ttu-id="638c3-250">[組み込みのコンバーターのソースコード](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="638c3-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="638c3-251">[System.Text.Json での DateTime と DateTimeOffset のサポート](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="638c3-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="638c3-252">[System.Text.Json の概要](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="638c3-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="638c3-253">[System.Text.Json の使用方法](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="638c3-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="638c3-254">[Newtonsoft.Json から移行する方法](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="638c3-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="638c3-255">[System.Text.Json API リファレンス](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="638c3-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="638c3-256">[System.Text.Json。シリアル化 API リファレンス](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="638c3-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->

---
title: JSON シリアル化のカスタムコンバーターを記述する方法-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 33d1cd7764e71d9e2fa382c9f3c5feb77e8defb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283346"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="99caf-102">.NET で JSON シリアル化のカスタムコンバーターを記述する方法</span><span class="sxs-lookup"><span data-stu-id="99caf-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="99caf-103">この記事では、<xref:System.Text.Json> 名前空間に用意されている JSON シリアル化クラスのカスタムコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99caf-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="99caf-104">`System.Text.Json`の概要については、「 [.net で JSON をシリアル化および逆シリアル化する方法](system-text-json-how-to.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99caf-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="99caf-105">*コンバーター*は、オブジェクトまたは値を JSON との間で変換するクラスです。</span><span class="sxs-lookup"><span data-stu-id="99caf-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="99caf-106">`System.Text.Json` 名前空間には、JavaScript プリミティブにマップされるほとんどのプリミティブ型用の組み込みのコンバーターがあります。</span><span class="sxs-lookup"><span data-stu-id="99caf-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="99caf-107">カスタムコンバーターは、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="99caf-107">You can write custom converters:</span></span>

* <span data-ttu-id="99caf-108">組み込みのコンバーターの既定の動作をオーバーライドする場合は。</span><span class="sxs-lookup"><span data-stu-id="99caf-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="99caf-109">たとえば、既定の ISO 8601-1:2019 形式ではなく、`DateTime` 値を mm/dd/yyyy 形式で表すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="99caf-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="99caf-110">カスタム値型をサポートする場合は。</span><span class="sxs-lookup"><span data-stu-id="99caf-110">To support a custom value type.</span></span> <span data-ttu-id="99caf-111">たとえば、`PhoneNumber` 構造体などです。</span><span class="sxs-lookup"><span data-stu-id="99caf-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="99caf-112">また、カスタムコンバーターを作成して、現在のリリースに含まれていない機能を使用して `System.Text.Json` を拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="99caf-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="99caf-113">この記事の後半では、次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="99caf-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="99caf-114">推論された[型をオブジェクトのプロパティに逆シリアル](#deserialize-inferred-types-to-object-properties)化します。</span><span class="sxs-lookup"><span data-stu-id="99caf-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="99caf-115">[文字列以外のキーを使用した辞書をサポート](#support-dictionary-with-non-string-key)します。</span><span class="sxs-lookup"><span data-stu-id="99caf-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="99caf-116">[ポリモーフィック逆シリアル化をサポート](#support-polymorphic-deserialization)します。</span><span class="sxs-lookup"><span data-stu-id="99caf-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="99caf-117">カスタムコンバーターパターン</span><span class="sxs-lookup"><span data-stu-id="99caf-117">Custom converter patterns</span></span>

<span data-ttu-id="99caf-118">カスタムコンバーターを作成するには、基本パターンとファクトリパターンという2つのパターンがあります。</span><span class="sxs-lookup"><span data-stu-id="99caf-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="99caf-119">ファクトリパターンは、型 `Enum` またはオープンジェネリックを処理するコンバーター用です。</span><span class="sxs-lookup"><span data-stu-id="99caf-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="99caf-120">基本パターンは、非ジェネリックおよびクローズジェネリック型用です。</span><span class="sxs-lookup"><span data-stu-id="99caf-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="99caf-121">たとえば、次の型のコンバーターには、ファクトリパターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="99caf-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="99caf-122">基本的なパターンによって処理できる型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99caf-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="99caf-123">基本パターンでは、1つの型を処理できるクラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="99caf-124">ファクトリパターンは、実行時に特定の型が必要であることを判断し、適切なコンバーターを動的に作成するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99caf-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="99caf-125">基本的なコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="99caf-125">Sample basic converter</span></span>

<span data-ttu-id="99caf-126">次のサンプルは、既存のデータ型の既定のシリアル化をオーバーライドするコンバーターです。</span><span class="sxs-lookup"><span data-stu-id="99caf-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="99caf-127">コンバーターでは、`DateTimeOffset` プロパティに mm/dd/yyyy 形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="99caf-128">サンプルファクトリパターンコンバーター</span><span class="sxs-lookup"><span data-stu-id="99caf-128">Sample factory pattern converter</span></span>

<span data-ttu-id="99caf-129">次のコードは、`Dictionary<Enum,TValue>`で動作するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="99caf-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="99caf-130">このコードは、最初のジェネリック型パラメーターが `Enum`、2番目のジェネリック型パラメーターが開いているため、ファクトリパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="99caf-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="99caf-131">`CanConvert` メソッドは、2つのジェネリックパラメーターを持つ `Dictionary` に対してのみ `true` を返します。最初のパラメーターは `Enum` 型です。</span><span class="sxs-lookup"><span data-stu-id="99caf-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="99caf-132">内部コンバーターは、`TValue`に対して実行時に提供されるいずれかの型を処理する既存のコンバーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="99caf-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="99caf-133">上記のコードは、この記事の後半で説明する[文字列以外のキーを使用したサポート辞書](#support-dictionary-with-non-string-key)に示されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="99caf-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="99caf-134">基本的なパターンに従う手順</span><span class="sxs-lookup"><span data-stu-id="99caf-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="99caf-135">次の手順では、基本的なパターンに従ってコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99caf-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="99caf-136">`T` がシリアル化および逆シリアル化される型である <xref:System.Text.Json.Serialization.JsonConverter%601> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99caf-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="99caf-137">`Read` メソッドをオーバーライドして受信 JSON を逆シリアル化し、型 `T`に変換します。</span><span class="sxs-lookup"><span data-stu-id="99caf-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="99caf-138">メソッドに渡された <xref:System.Text.Json.Utf8JsonReader> を使用して、JSON を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="99caf-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="99caf-139">`Write` メソッドをオーバーライドして、`T`型の受信オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="99caf-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="99caf-140">メソッドに渡された <xref:System.Text.Json.Utf8JsonWriter> を使用して JSON を記述します。</span><span class="sxs-lookup"><span data-stu-id="99caf-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="99caf-141">`CanConvert` メソッドは、必要な場合にのみオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="99caf-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="99caf-142">変換する型が `T`型の場合、既定の実装は `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="99caf-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="99caf-143">したがって、型 `T` だけをサポートするコンバーターは、このメソッドをオーバーライドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="99caf-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="99caf-144">このメソッドをオーバーライドする必要があるコンバーターの例については、この記事で後述する「[ポリモーフィックな逆シリアル化](#support-polymorphic-deserialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99caf-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="99caf-145">[組み込みのコンバーターソースコード](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)は、カスタムコンバーターを作成するための参照の実装として参照できます。</span><span class="sxs-lookup"><span data-stu-id="99caf-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="99caf-146">ファクトリパターンに従う手順</span><span class="sxs-lookup"><span data-stu-id="99caf-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="99caf-147">次の手順では、ファクトリパターンに従ってコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99caf-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="99caf-148"><xref:System.Text.Json.Serialization.JsonConverterFactory> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99caf-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="99caf-149">変換する型が、コンバーターが処理できる型である場合に true を返すように `CanConvert` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="99caf-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="99caf-150">たとえば、コンバーターが `List<T>` 用の場合、`List<int>`、`List<string>`、および `List<DateTime>`だけを処理できます。</span><span class="sxs-lookup"><span data-stu-id="99caf-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="99caf-151">`CreateConverter` メソッドをオーバーライドして、実行時に提供される変換の種類を処理するコンバータークラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="99caf-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="99caf-152">`CreateConverter` メソッドによってインスタンス化されるコンバータークラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99caf-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="99caf-153">オブジェクトを文字列との間で変換するコードはすべての型で同じではないため、オープンジェネリックにはファクトリパターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="99caf-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="99caf-154">オープンジェネリック型 (`List<T>`など) のコンバーターは、背後にあるクローズジェネリック型 (`List<DateTime>`など) のコンバーターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="99caf-155">コードは、コンバーターが処理できる各閉じられたジェネリック型を処理するように記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="99caf-156">`Enum` 型はオープンジェネリック型に似ています。 `Enum` のコンバーターは、シーンの背後にある特定の `Enum` (`WeekdaysEnum`など) のコンバーターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="99caf-157">エラー処理</span><span class="sxs-lookup"><span data-stu-id="99caf-157">Error handling</span></span>

<span data-ttu-id="99caf-158">エラー処理コードで例外をスローする必要がある場合は、メッセージを使用せずに <xref:System.Text.Json.JsonException> をスローすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="99caf-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="99caf-159">この例外の種類では、エラーの原因となった JSON の部分へのパスを含むメッセージが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="99caf-160">たとえば、ステートメント `throw new JsonException();` では、次の例のようなエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="99caf-161">メッセージ (`throw new JsonException("Error occurred")`など) を指定した場合でも、例外は <xref:System.Text.Json.JsonException.Path> プロパティのパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="99caf-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="99caf-162">カスタムコンバーターを登録する</span><span class="sxs-lookup"><span data-stu-id="99caf-162">Register a custom converter</span></span>

<span data-ttu-id="99caf-163">カスタムコンバーターを*登録*して、`Serialize` および `Deserialize` メソッドで使用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="99caf-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="99caf-164">次のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="99caf-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="99caf-165">コンバータークラスのインスタンスを <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="99caf-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="99caf-166">カスタムコンバーターを必要とするプロパティに[[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="99caf-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="99caf-167">[[Jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)属性をカスタム値型を表すクラスまたは構造体に適用します。</span><span class="sxs-lookup"><span data-stu-id="99caf-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="99caf-168">登録サンプル-コンバーターコレクション</span><span class="sxs-lookup"><span data-stu-id="99caf-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="99caf-169"><xref:System.DateTimeOffset>型のプロパティの既定値 <xref:System.ComponentModel.DateTimeOffsetConverter> する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99caf-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="99caf-170">次の型のインスタンスをシリアル化するとします。</span><span class="sxs-lookup"><span data-stu-id="99caf-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="99caf-171">カスタムコンバーターが使用されたことを示す JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99caf-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="99caf-172">次のコードでは、カスタム `DateTimeOffset` コンバーターを使用して逆シリアル化するのと同じアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="99caf-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="99caf-173">登録のサンプル-[JsonConverter] プロパティ</span><span class="sxs-lookup"><span data-stu-id="99caf-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="99caf-174">次のコードでは、`Date` プロパティのカスタムコンバーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="99caf-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="99caf-175">`WeatherForecastWithConverterAttribute` をシリアル化するコードでは、`JsonSerializeOptions.Converters`を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="99caf-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="99caf-176">逆シリアル化するコードでは、`Converters`を使用する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="99caf-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="99caf-177">登録サンプル-[JsonConverter] 型</span><span class="sxs-lookup"><span data-stu-id="99caf-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="99caf-178">次に、構造体を作成し、それに `[JsonConverter]` 属性を適用するコードを示します。</span><span class="sxs-lookup"><span data-stu-id="99caf-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="99caf-179">前の構造体のカスタムコンバーターは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="99caf-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="99caf-180">構造体の `[JsonConvert]` 属性は、`Temperature`型のプロパティの既定値としてカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="99caf-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="99caf-181">コンバーターは、シリアル化または逆シリアル化するときに、次の型の `TemperatureCelsius` プロパティで自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="99caf-182">コンバーターの登録の優先順位</span><span class="sxs-lookup"><span data-stu-id="99caf-182">Converter registration precedence</span></span>

<span data-ttu-id="99caf-183">シリアル化または逆シリアル化の際には、次の順序で JSON 要素ごとにコンバーターが選択され、最も高い優先度から順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="99caf-184">`[JsonConverter]` プロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="99caf-185">`Converters` コレクションに追加されたコンバーター。</span><span class="sxs-lookup"><span data-stu-id="99caf-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="99caf-186">`[JsonConverter]` カスタム値型または POCO に適用されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="99caf-187">1つの型に対して複数のカスタムコンバーターが `Converters` コレクションに登録されている場合、`CanConvert` に対して true を返す最初のコンバーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="99caf-188">組み込みのコンバーターは、適用可能なカスタムコンバーターが登録されていない場合にのみ選択されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="99caf-189">一般的なシナリオのコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="99caf-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="99caf-190">以下のセクションでは、組み込み機能で処理されない一般的なシナリオに対処するコンバーターのサンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="99caf-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="99caf-191">推論された型のオブジェクトプロパティへの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="99caf-191">Deserialize inferred types to Object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="99caf-192">文字列以外のキーを使用したサポート辞書</span><span class="sxs-lookup"><span data-stu-id="99caf-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="99caf-193">ポリモーフィック逆シリアル化のサポート</span><span class="sxs-lookup"><span data-stu-id="99caf-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="99caf-194">推論された型のオブジェクトプロパティへの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="99caf-194">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="99caf-195">`Object`型のプロパティに逆シリアル化すると、`JsonElement` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-195">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="99caf-196">その理由は、デシリアライザーは、作成する CLR 型を認識しないため、推測しようとしません。</span><span class="sxs-lookup"><span data-stu-id="99caf-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="99caf-197">たとえば、JSON プロパティに "true" が含まれている場合、デシリアライザーは、値が `Boolean`であることを推論しません。また、要素に "01/01/2019" がある場合、デシリアライザーは `DateTime`であることを推論しません。</span><span class="sxs-lookup"><span data-stu-id="99caf-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="99caf-198">型の推定は不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="99caf-199">デシリアライザーが、小数点のない JSON 番号を `long`として解析する場合、値が最初に `ulong` または `BigInteger`としてシリアル化された場合、範囲外の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="99caf-200">数値が最初に `decimal`としてシリアル化された場合、`double` として小数点がある数値を解析すると、精度が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="99caf-201">型の推定が必要なシナリオでは、次のコードは `Object` プロパティのカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="99caf-201">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="99caf-202">コードは次のように変換します。</span><span class="sxs-lookup"><span data-stu-id="99caf-202">The code converts:</span></span>

* <span data-ttu-id="99caf-203">`true` と `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="99caf-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="99caf-204">`long` または `double` する数値</span><span class="sxs-lookup"><span data-stu-id="99caf-204">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="99caf-205">`DateTime` する日付</span><span class="sxs-lookup"><span data-stu-id="99caf-205">Dates to `DateTime`</span></span>
* <span data-ttu-id="99caf-206">`string` する文字列</span><span class="sxs-lookup"><span data-stu-id="99caf-206">Strings to `string`</span></span>
* <span data-ttu-id="99caf-207">他のすべての `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="99caf-207">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="99caf-208">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="99caf-208">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="99caf-209">`Object` プロパティを持つ型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99caf-209">Here's an example type with `Object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="99caf-210">次の JSON の例には、`DateTime`、`long`、および `string`として逆シリアル化される値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99caf-210">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="99caf-211">カスタムコンバーターを使用しない場合、逆シリアル化によって各プロパティに `JsonElement` が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="99caf-211">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="99caf-212">`System.Text.Json.Serialization` 名前空間の[単体テストフォルダー](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)には、オブジェクトプロパティへの逆シリアル化を処理するカスタムコンバーターの例が多数あります。</span><span class="sxs-lookup"><span data-stu-id="99caf-212">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="99caf-213">文字列以外のキーを使用したサポート辞書</span><span class="sxs-lookup"><span data-stu-id="99caf-213">Support Dictionary with non-string key</span></span>

<span data-ttu-id="99caf-214">ディクショナリコレクションの組み込みサポートは `Dictionary<string, TValue>`用です。</span><span class="sxs-lookup"><span data-stu-id="99caf-214">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="99caf-215">つまり、キーは文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-215">That is, the key must be a string.</span></span> <span data-ttu-id="99caf-216">キーとして整数またはその他の型を持つディクショナリをサポートするには、カスタムコンバーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="99caf-216">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="99caf-217">次のコードは、`Dictionary<Enum,TValue>`で動作するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="99caf-217">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="99caf-218">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="99caf-218">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="99caf-219">コンバーターは、次の `Enum`を使用する次のクラスの `TemperatureRanges` プロパティをシリアル化および逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="99caf-219">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="99caf-220">シリアル化からの JSON 出力は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="99caf-220">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="99caf-221">`System.Text.Json.Serialization` 名前空間の[単体テストフォルダー](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)には、文字列キー以外のディクショナリを処理するカスタムコンバーターの例が多数あります。</span><span class="sxs-lookup"><span data-stu-id="99caf-221">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="99caf-222">ポリモーフィック逆シリアル化のサポート</span><span class="sxs-lookup"><span data-stu-id="99caf-222">Support polymorphic deserialization</span></span>

<span data-ttu-id="99caf-223">[ポリモーフィックなシリアル化](system-text-json-how-to.md#serialize-properties-of-derived-classes)ではカスタムコンバーターは必要ありませんが、逆シリアル化にはカスタムコンバーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="99caf-223">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="99caf-224">たとえば、`Person` 抽象基本クラスがあり、`Employee` および `Customer` 派生クラスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="99caf-224">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="99caf-225">ポリモーフィックな逆シリアル化とは、デザイン時に `Person` を逆シリアル化ターゲットとして指定できること、および JSON 内の `Customer` オブジェクトと `Employee` オブジェクトが実行時に正しく逆シリアル化されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="99caf-225">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="99caf-226">逆シリアル化中に、JSON で必要な型を識別する手掛かりを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-226">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="99caf-227">使用できる手掛かりの種類は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="99caf-227">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="99caf-228">たとえば、識別子のプロパティを使用できる場合や、特定のプロパティの有無に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="99caf-228">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="99caf-229">`System.Text.Json` の現在のリリースでは、ポリモーフィックな逆シリアル化のシナリオを処理する方法を指定する属性が提供されないため、カスタムコンバーターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="99caf-229">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="99caf-230">次のコードは、基底クラス、2つの派生クラス、およびそれらのカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="99caf-230">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="99caf-231">コンバーターは、ポリモーフィックな逆シリアル化を行うために識別子プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="99caf-231">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="99caf-232">型識別子はクラス定義に含まれていませんが、シリアル化中に作成され、逆シリアル化中に読み取られます。</span><span class="sxs-lookup"><span data-stu-id="99caf-232">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="99caf-233">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="99caf-233">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="99caf-234">コンバーターは、同じコンバーターを使用して作成された JSON を逆シリアル化できます。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="99caf-234">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="99caf-235">その他のカスタムコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="99caf-235">Other custom converter samples</span></span>

<span data-ttu-id="99caf-236">`System.Text.Json.Serialization` ソースコードの[単体テストフォルダー](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)には、次のような他のカスタムコンバーターのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99caf-236">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="99caf-237">逆シリアル化時に null を0に変換する `Int32` コンバーター</span><span class="sxs-lookup"><span data-stu-id="99caf-237">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="99caf-238">逆シリアル化時に文字列と数値の両方を許可する `Int32` コンバーター</span><span class="sxs-lookup"><span data-stu-id="99caf-238">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="99caf-239">`Enum` コンバーター</span><span class="sxs-lookup"><span data-stu-id="99caf-239">`Enum` converter</span></span>
* <span data-ttu-id="99caf-240">外部データを受け入れる `List<T>` コンバーター</span><span class="sxs-lookup"><span data-stu-id="99caf-240">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="99caf-241">コンマで区切られた数値のリストを処理する `Long[]` コンバーター</span><span class="sxs-lookup"><span data-stu-id="99caf-241">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="99caf-242">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="99caf-242">Additional resources</span></span>

* [<span data-ttu-id="99caf-243">System.string の概要</span><span class="sxs-lookup"><span data-stu-id="99caf-243">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="99caf-244">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="99caf-244">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="99caf-245">方法: system.string を使用する</span><span class="sxs-lookup"><span data-stu-id="99caf-245">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="99caf-246">組み込みのコンバーターのソースコード</span><span class="sxs-lookup"><span data-stu-id="99caf-246">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="99caf-247">`System.Text.Json` のカスタムコンバーターに関連する GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="99caf-247">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="99caf-248">36639カスタムコンバーターの概要</span><span class="sxs-lookup"><span data-stu-id="99caf-248">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="99caf-249">38713オブジェクトへの逆シリアル化について</span><span class="sxs-lookup"><span data-stu-id="99caf-249">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="99caf-250">40120非文字列キー辞書について</span><span class="sxs-lookup"><span data-stu-id="99caf-250">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="99caf-251">37787ポリモーフィック逆シリアル化について</span><span class="sxs-lookup"><span data-stu-id="99caf-251">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)

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
ms.openlocfilehash: 361818a0bda8863f8878b86e5fb377dc0faf5246
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73741904"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="a0c8b-102">.NET で JSON シリアル化のカスタムコンバーターを記述する方法</span><span class="sxs-lookup"><span data-stu-id="a0c8b-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="a0c8b-103">この記事では、<xref:System.Text.Json> 名前空間に用意されている JSON シリアル化クラスのカスタムコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="a0c8b-104">`System.Text.Json`の概要については、「 [.net で JSON をシリアル化および逆シリアル化する方法](system-text-json-how-to.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="a0c8b-105">*コンバーター*は、オブジェクトまたは値を JSON との間で変換するクラスです。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="a0c8b-106">`System.Text.Json` 名前空間には、JavaScript プリミティブにマップされるほとんどのプリミティブ型用の組み込みのコンバーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="a0c8b-107">カスタムコンバーターは、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-107">You can write custom converters:</span></span>

* <span data-ttu-id="a0c8b-108">組み込みのコンバーターの既定の動作をオーバーライドする場合は。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="a0c8b-109">たとえば、既定の ISO 8601-1:2019 形式ではなく、`DateTime` 値を mm/dd/yyyy 形式で表すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="a0c8b-110">カスタム値型をサポートする場合は。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-110">To support a custom value type.</span></span> <span data-ttu-id="a0c8b-111">たとえば、`PhoneNumber` 構造体などです。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="a0c8b-112">また、カスタムコンバーターを作成して、現在のリリースに含まれていない機能を使用して `System.Text.Json` を拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="a0c8b-113">この記事の後半では、次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="a0c8b-114">推論された[型をオブジェクトのプロパティに逆シリアル](#deserialize-inferred-types-to-object-properties)化します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="a0c8b-115">[文字列以外のキーを使用した辞書をサポート](#support-dictionary-with-non-string-key)します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="a0c8b-116">[ポリモーフィック逆シリアル化をサポート](#support-polymorphic-deserialization)します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="a0c8b-117">カスタムコンバーターパターン</span><span class="sxs-lookup"><span data-stu-id="a0c8b-117">Custom converter patterns</span></span>

<span data-ttu-id="a0c8b-118">カスタムコンバーターを作成するには、基本パターンとファクトリパターンという2つのパターンがあります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="a0c8b-119">ファクトリパターンは、型 `Enum` またはオープンジェネリックを処理するコンバーター用です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="a0c8b-120">基本パターンは、非ジェネリックおよびクローズジェネリック型用です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="a0c8b-121">たとえば、次の型のコンバーターには、ファクトリパターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="a0c8b-122">基本的なパターンによって処理できる型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="a0c8b-123">基本パターンでは、1つの型を処理できるクラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="a0c8b-124">ファクトリパターンは、実行時に特定の型が必要であることを判断し、適切なコンバーターを動的に作成するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="a0c8b-125">基本的なコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="a0c8b-125">Sample basic converter</span></span>

<span data-ttu-id="a0c8b-126">次のサンプルは、既存のデータ型の既定のシリアル化をオーバーライドするコンバーターです。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="a0c8b-127">コンバーターでは、`DateTimeOffset` プロパティに mm/dd/yyyy 形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

```csharp
private class ExampleDateTimeOffsetConverter : JsonConverter<DateTimeOffset>
{
    public override DateTimeOffset Read(
        ref Utf8JsonReader reader, 
        Type typeToConvert, 
        JsonSerializerOptions options)
    {
        return DateTimeOffset.ParseExact(reader.GetString(), 
            "MM/dd/yyyy", CultureInfo.InvariantCulture);
    }

    public override void Write(
        Utf8JsonWriter writer, 
        DateTimeOffset value, 
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString(
            "MM/dd/yyyy", CultureInfo.InvariantCulture));
    }
}
```

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="a0c8b-128">サンプルファクトリパターンコンバーター</span><span class="sxs-lookup"><span data-stu-id="a0c8b-128">Sample factory pattern converter</span></span>

<span data-ttu-id="a0c8b-129">次のコードは、`Dictionary<Enum,TValue>`で動作するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="a0c8b-130">このコードは、最初のジェネリック型パラメーターが `Enum`、2番目のジェネリック型パラメーターが開いているため、ファクトリパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="a0c8b-131">`CanConvert` メソッドは、2つのジェネリックパラメーターを持つ `Dictionary` に対してのみ `true` を返します。最初のパラメーターは `Enum` 型です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="a0c8b-132">内部コンバーターは、`TValue`に対して実行時に提供されるいずれかの型を処理する既存のコンバーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

<span data-ttu-id="a0c8b-133">上記のコードは、この記事の後半で説明する[文字列以外のキーを使用したサポート辞書](#support-dictionary-with-non-string-key)に示されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="a0c8b-134">基本的なパターンに従う手順</span><span class="sxs-lookup"><span data-stu-id="a0c8b-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="a0c8b-135">次の手順では、基本的なパターンに従ってコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="a0c8b-136">`T` がシリアル化および逆シリアル化される型である <xref:System.Text.Json.Serialization.JsonConverter%601> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="a0c8b-137">`Read` メソッドをオーバーライドして受信 JSON を逆シリアル化し、型 `T`に変換します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="a0c8b-138">メソッドに渡された <xref:System.Text.Json.Utf8JsonReader> を使用して、JSON を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="a0c8b-139">`Write` メソッドをオーバーライドして、`T`型の受信オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="a0c8b-140">メソッドに渡された <xref:System.Text.Json.Utf8JsonWriter> を使用して JSON を記述します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="a0c8b-141">`CanConvert` メソッドは、必要な場合にのみオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="a0c8b-142">変換する型が `T`型の場合、既定の実装は `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="a0c8b-143">したがって、型 `T` だけをサポートするコンバーターは、このメソッドをオーバーライドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="a0c8b-144">このメソッドをオーバーライドする必要があるコンバーターの例については、この記事で後述する「[ポリモーフィックな逆シリアル化](#support-polymorphic-deserialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="a0c8b-145">[組み込みのコンバーターソースコード](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)は、カスタムコンバーターを作成するための参照の実装として参照できます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="a0c8b-146">ファクトリパターンに従う手順</span><span class="sxs-lookup"><span data-stu-id="a0c8b-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="a0c8b-147">次の手順では、ファクトリパターンに従ってコンバーターを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="a0c8b-148"><xref:System.Text.Json.Serialization.JsonConverterFactory> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="a0c8b-149">変換する型が、コンバーターが処理できる型である場合に true を返すように `CanConvert` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="a0c8b-150">たとえば、コンバーターが `List<T>` 用の場合、`List<int>`、`List<string>`、および `List<DateTime>`だけを処理できます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="a0c8b-151">`CreateConverter` メソッドをオーバーライドして、実行時に提供される変換の種類を処理するコンバータークラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="a0c8b-152">`CreateConverter` メソッドによってインスタンス化されるコンバータークラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="a0c8b-153">オブジェクトを文字列との間で変換するコードはすべての型で同じではないため、オープンジェネリックにはファクトリパターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="a0c8b-154">オープンジェネリック型 (`List<T>`など) のコンバーターは、背後にあるクローズジェネリック型 (`List<DateTime>`など) のコンバーターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="a0c8b-155">コードは、コンバーターが処理できる各閉じられたジェネリック型を処理するように記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="a0c8b-156">`Enum` 型はオープンジェネリック型に似ています。 `Enum` のコンバーターは、シーンの背後にある特定の `Enum` (`WeekdaysEnum`など) のコンバーターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="a0c8b-157">エラー処理</span><span class="sxs-lookup"><span data-stu-id="a0c8b-157">Error handling</span></span>

<span data-ttu-id="a0c8b-158">エラー処理コードで例外をスローする必要がある場合は、メッセージを使用せずに <xref:System.Text.Json.JsonException> をスローすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="a0c8b-159">この例外の種類では、エラーの原因となった JSON の部分へのパスを含むメッセージが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="a0c8b-160">たとえば、ステートメント `throw new JsonException();` では、次の例のようなエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="a0c8b-161">メッセージ (`throw new JsonException("Error occurred)`など) を指定した場合でも、例外は <xref:System.Text.Json.JsonException.Path> プロパティのパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-161">If you do provide a message (for example, `throw new JsonException("Error occurred)`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="a0c8b-162">カスタムコンバーターを登録する</span><span class="sxs-lookup"><span data-stu-id="a0c8b-162">Register a custom converter</span></span>

<span data-ttu-id="a0c8b-163">カスタムコンバーターを*登録*して、`Serialize` および `Deserialize` メソッドで使用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="a0c8b-164">次のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="a0c8b-165">コンバータークラスのインスタンスを <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="a0c8b-166">カスタムコンバーターを必要とするプロパティに[[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="a0c8b-167">[[Jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)属性をカスタム値型を表すクラスまたは構造体に適用します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="a0c8b-168">登録サンプル-コンバーターコレクション</span><span class="sxs-lookup"><span data-stu-id="a0c8b-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="a0c8b-169">`DateTimeOffset`型のプロパティの既定値 `ExampleDateTimeOffsetConverter` する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-169">Here's an example that makes the `ExampleDateTimeOffsetConverter` the default for properties of type `DateTimeOffset`:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="a0c8b-170">次の型をシリアル化するとします。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-170">Suppose you serialize the following type:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="a0c8b-171">カスタムコンバーターが使用されたことを示す JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="a0c8b-172">次のコードでは、カスタム `DateTimeOffset` コンバーターを使用して逆シリアル化するのと同じアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="a0c8b-173">登録のサンプル-[JsonConverter] プロパティ</span><span class="sxs-lookup"><span data-stu-id="a0c8b-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="a0c8b-174">次のコードでは、`Date` プロパティのカスタムコンバーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-174">The following code selects a custom converter for the `Date` property:</span></span>

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="a0c8b-175">`WeatherForecastWithConverter` をシリアル化および逆シリアル化するコードでは、`JsonSerializeOptions.Converters`を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-175">The code to serialize and deserialize `WeatherForecastWithConverter` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="a0c8b-176">登録サンプル-[JsonConverter] 型</span><span class="sxs-lookup"><span data-stu-id="a0c8b-176">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="a0c8b-177">次に、構造体を作成し、それに `[JsonConverter]` 属性を適用するコードを示します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-177">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

```csharp
[JsonConverter(typeof(TemperatureConverter))]
public struct Temperature
{
    public Temperature(int degrees, bool celsius)
    {
        _degrees = degrees;
        _isCelsius = celsius;
    }
    private bool _isCelsius;
    private int _degrees;
    public int Degrees => _degrees;
    public bool IsCelsius => _isCelsius; 
    public bool IsFahrenheit => !_isCelsius;
    public override string ToString() =>
        $"{_degrees.ToString()}{(_isCelsius ? "C" : "F")}";
    public static Temperature Parse(string input)
    {
        int degrees = int.Parse(input.Substring(0, input.Length - 1));
        bool celsius = (input.Substring(input.Length - 1) == "C");
        return new Temperature(degrees, celsius);
    }
}
```

<span data-ttu-id="a0c8b-178">前の構造体のカスタムコンバーターは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-178">Here's the custom converter for the preceding struct:</span></span>

```csharp
public class TemperatureConverter : JsonConverter<Temperature>
{
    public override Temperature Read(
        ref Utf8JsonReader reader,
        Type typeToConvert,
        JsonSerializerOptions options)
    {
        Debug.Assert(typeToConvert == typeof(Temperature));
        return Temperature.Parse(reader.GetString());
    }

    public override void Write(
        Utf8JsonWriter writer,
        Temperature value,
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString());
    }
}
```

<span data-ttu-id="a0c8b-179">構造体の `[JsonConvert]` 属性は、`Temperature`型のプロパティの既定値としてカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-179">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="a0c8b-180">コンバーターは、シリアル化または逆シリアル化するときに、次の型の `TemperatureC` プロパティで自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-180">The converter is automatically used on the `TemperatureC` property of the following type when you serialize or deserialize it:</span></span>

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a><span data-ttu-id="a0c8b-181">コンバーターの登録の優先順位</span><span class="sxs-lookup"><span data-stu-id="a0c8b-181">Converter registration precedence</span></span>

<span data-ttu-id="a0c8b-182">シリアル化または逆シリアル化の際には、次の順序で JSON 要素ごとにコンバーターが選択され、最も高い優先度から順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-182">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="a0c8b-183">`[JsonConverter]` プロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-183">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="a0c8b-184">`Converters` コレクションに追加されたコンバーター。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-184">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="a0c8b-185">`[JsonConverter]` カスタム値型または POCO に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-185">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="a0c8b-186">1つの型に対して複数のカスタムコンバーターが `Converters` コレクションに登録されている場合、`CanConvert` に対して true を返す最初のコンバーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-186">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="a0c8b-187">組み込みのコンバーターは、適用可能なカスタムコンバーターが登録されていない場合にのみ選択されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-187">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="a0c8b-188">一般的なシナリオのコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="a0c8b-188">Converter samples for common scenarios</span></span>

<span data-ttu-id="a0c8b-189">以下のセクションでは、組み込み機能で処理されない一般的なシナリオに対処するコンバーターのサンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-189">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="a0c8b-190">推論された型のオブジェクトプロパティへの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="a0c8b-190">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="a0c8b-191">`Object`型のプロパティに逆シリアル化すると、`JsonElement` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-191">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="a0c8b-192">その理由は、デシリアライザーは、作成する CLR 型を認識しないため、推測しようとしません。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-192">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="a0c8b-193">たとえば、JSON プロパティに "true" が含まれている場合、デシリアライザーは、値が `Boolean`であることを推論しません。また、要素に "01/01/2019" がある場合、デシリアライザーは `DateTime`であることを推論しません。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-193">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="a0c8b-194">型の推定は不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-194">Type inference can be inaccurate.</span></span> <span data-ttu-id="a0c8b-195">デシリアライザーが、小数点のない JSON 番号を `long`として解析する場合、値が最初に `ulong` または `BigInteger`としてシリアル化された場合、範囲外の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-195">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="a0c8b-196">数値が最初に `decimal`としてシリアル化された場合、`double` として小数点がある数値を解析すると、精度が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-196">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="a0c8b-197">型の推定が必要なシナリオでは、次のコードは `Object` プロパティのカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-197">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="a0c8b-198">コードは次のように変換します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-198">The code converts:</span></span>

* <span data-ttu-id="a0c8b-199">`true` と `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="a0c8b-199">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="a0c8b-200">`long` または `double` する数値</span><span class="sxs-lookup"><span data-stu-id="a0c8b-200">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="a0c8b-201">`DateTime` する日付</span><span class="sxs-lookup"><span data-stu-id="a0c8b-201">Dates to `DateTime`</span></span>
* <span data-ttu-id="a0c8b-202">`string` する文字列</span><span class="sxs-lookup"><span data-stu-id="a0c8b-202">Strings to `string`</span></span>
* <span data-ttu-id="a0c8b-203">他のすべての `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="a0c8b-203">Everything else to `JsonElement`</span></span>

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ObjectToInferredTypesConverter
        : JsonConverter<object>
    {
        public override object Read(
            ref Utf8JsonReader reader,
            Type typeToConvert,
            JsonSerializerOptions options)
        {
            if (reader.TokenType == JsonTokenType.True)
            {
                return true;
            }

            if (reader.TokenType == JsonTokenType.False)
            {
                return false;
            }

            if (reader.TokenType == JsonTokenType.Number)
            {
                if (reader.TryGetInt64(out long l))
                {
                    return l;
                }

                return reader.GetDouble();
            }

            if (reader.TokenType == JsonTokenType.String)
            {
                if (reader.TryGetDateTime(out DateTime datetime))
                {
                    return datetime;
                }

                return reader.GetString();
            }

            // Use JsonElement as fallback.
            // Newtonsoft uses JArray or JObject.
            using (JsonDocument document = JsonDocument.ParseValue(ref reader))
            {
                return document.RootElement.Clone();
            }
        }

        public override void Write(
            Utf8JsonWriter writer,
            object value,
            JsonSerializerOptions options)
        {
            throw new InvalidOperationException("Should not get here.");
        }
    }
}
```

<span data-ttu-id="a0c8b-204">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-204">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

<span data-ttu-id="a0c8b-205">オブジェクトプロパティを持つ型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-205">Here's an example type with an Object property:</span></span>

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

<span data-ttu-id="a0c8b-206">次の JSON の例には、`DateTime`、`long`、および `string`として逆シリアル化される値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-206">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="a0c8b-207">カスタムコンバーターを使用しない場合、逆シリアル化によって各プロパティに `JsonElement` が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-207">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="a0c8b-208">`System.Text.Json.Serialization` 名前空間の[単体テストフォルダー](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)には、オブジェクトプロパティへの逆シリアル化を処理するカスタムコンバーターの例が多数あります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-208">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="a0c8b-209">文字列以外のキーを使用したサポート辞書</span><span class="sxs-lookup"><span data-stu-id="a0c8b-209">Support Dictionary with non-string key</span></span>

<span data-ttu-id="a0c8b-210">ディクショナリコレクションの組み込みサポートは `Dictionary<string, TValue>`用です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-210">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="a0c8b-211">つまり、キーは文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-211">That is, the key must be a string.</span></span> <span data-ttu-id="a0c8b-212">キーとして整数またはその他の型を持つディクショナリをサポートするには、カスタムコンバーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-212">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="a0c8b-213">次のコードは、`Dictionary<Enum,TValue>`で動作するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-213">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

<span data-ttu-id="a0c8b-214">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-214">The following code registers the converter:</span></span>

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

<span data-ttu-id="a0c8b-215">コンバーターは、次の `Enum`を使用する次のクラスの `TemperatureRanges` プロパティをシリアル化および逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-215">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

```csharp
public class WeatherForecastWithEnumDictionary
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public Dictionary<SummaryWordsEnum, int> TemperatureRanges { get; set; }
}

public enum SummaryWordsEnum
{
    Cold, Hot
}
```

<span data-ttu-id="a0c8b-216">シリアル化からの JSON 出力は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-216">The JSON output from serialization looks like the following example:</span></span>

```json
{

  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="a0c8b-217">`System.Text.Json.Serialization` 名前空間の[単体テストフォルダー](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)には、文字列キー以外のディクショナリを処理するカスタムコンバーターの例が多数あります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-217">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="a0c8b-218">ポリモーフィック逆シリアル化のサポート</span><span class="sxs-lookup"><span data-stu-id="a0c8b-218">Support polymorphic deserialization</span></span>

<span data-ttu-id="a0c8b-219">[ポリモーフィックなシリアル化](system-text-json-how-to.md#serialize-properties-of-derived-classes)ではカスタムコンバーターは必要ありませんが、逆シリアル化にはカスタムコンバーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-219">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="a0c8b-220">たとえば、`Person` 抽象基本クラスがあり、`Employee` および `Customer` 派生クラスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-220">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="a0c8b-221">ポリモーフィックな逆シリアル化とは、デザイン時に `Person` を逆シリアル化ターゲットとして指定できること、および JSON 内の `Customer` オブジェクトと `Employee` オブジェクトが実行時に正しく逆シリアル化されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-221">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="a0c8b-222">逆シリアル化中に、JSON で必要な型を識別する手掛かりを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-222">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="a0c8b-223">使用できる手掛かりの種類は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-223">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="a0c8b-224">たとえば、識別子のプロパティを使用できる場合や、特定のプロパティの有無に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-224">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="a0c8b-225">`System.Text.Json` の現在のリリースでは、ポリモーフィックな逆シリアル化のシナリオを処理する方法を指定する属性が提供されないため、カスタムコンバーターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-225">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="a0c8b-226">次のコードは、基底クラス、2つの派生クラス、およびそれらのカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-226">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="a0c8b-227">コンバーターは、ポリモーフィックな逆シリアル化を行うために識別子プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-227">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="a0c8b-228">型識別子はクラス定義に含まれていませんが、シリアル化中に作成され、逆シリアル化中に読み取られます。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-228">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

```csharp
public class Person
{
    public string Name { get; set; }
}

public class Customer : Person
{
    public decimal CreditLimit { get; set; }
}

public class Employee : Person
{
    public string OfficeNumber { get; set; }
}
```

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class PersonConverterWithTypeDiscriminator : JsonConverter<Person>
    {
        enum TypeDiscriminator
        {
            Customer = 1,
            Employee = 2
        }

        public override bool CanConvert(Type typeToConvert)
        {
            return typeof(Person).IsAssignableFrom(typeToConvert);
        }

        public override Person Read(ref Utf8JsonReader reader, Type typeToConvert, JsonSerializerOptions options)
        {
            if (reader.TokenType != JsonTokenType.StartObject)
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.PropertyName)
            {
                throw new JsonException();
            }

            string propertyName = reader.GetString();
            if (propertyName != "TypeDiscriminator")
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.Number)
            {
                throw new JsonException();
            }

            Person value;
            TypeDiscriminator typeDiscriminator = (TypeDiscriminator)reader.GetInt32();
            switch (typeDiscriminator)
            {
                case TypeDiscriminator.Customer:
                    value = new Customer();
                    break;

                case TypeDiscriminator.Employee:
                    value = new Employee();
                    break;

                default:
                    throw new JsonException();
            }

            while (reader.Read())
            {
                if (reader.TokenType == JsonTokenType.EndObject)
                {
                    return value;
                }

                if (reader.TokenType == JsonTokenType.PropertyName)
                {
                    propertyName = reader.GetString();
                    reader.Read();
                    switch (propertyName)
                    {
                        case "CreditLimit":
                            decimal creditLimit = reader.GetDecimal();
                            ((Customer)value).CreditLimit = creditLimit;
                            break;
                        case "OfficeNumber":
                            string officeNumber = reader.GetString();
                            ((Employee)value).OfficeNumber = officeNumber;
                            break;
                        case "Name":
                            string name = reader.GetString();
                            value.Name = name;
                            break;
                    }
                }
            }

            throw new JsonException();
        }

        public override void Write(Utf8JsonWriter writer, Person value, JsonSerializerOptions options)
        {
            writer.WriteStartObject();

            if (value is Customer customer)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Customer);
                writer.WriteNumber("CreditLimit", customer.CreditLimit);
            }
            else if (value is Employee employee)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Employee);
                writer.WriteString("OfficeNumber", employee.OfficeNumber);
            }

            writer.WriteString("Name", value.Name);

            writer.WriteEndObject();
        }
    }
}
```

<span data-ttu-id="a0c8b-229">次のコードは、コンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-229">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

<span data-ttu-id="a0c8b-230">コンバーターは、同じコンバーターを使用して作成された JSON を逆シリアル化できます。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-230">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="a0c8b-231">その他のカスタムコンバーターのサンプル</span><span class="sxs-lookup"><span data-stu-id="a0c8b-231">Other custom converter samples</span></span>

<span data-ttu-id="a0c8b-232">`System.Text.Json.Serialization` ソースコードの[単体テストフォルダー](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)には、次のような他のカスタムコンバーターのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0c8b-232">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="a0c8b-233">逆シリアル化時に null を0に変換する `Int32` コンバーター</span><span class="sxs-lookup"><span data-stu-id="a0c8b-233">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="a0c8b-234">逆シリアル化時に文字列と数値の両方を許可する `Int32` コンバーター</span><span class="sxs-lookup"><span data-stu-id="a0c8b-234">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="a0c8b-235">`Enum` コンバーター</span><span class="sxs-lookup"><span data-stu-id="a0c8b-235">`Enum` converter</span></span>
* <span data-ttu-id="a0c8b-236">外部データを受け入れる `List<T>` コンバーター</span><span class="sxs-lookup"><span data-stu-id="a0c8b-236">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="a0c8b-237">コンマで区切られた数値のリストを処理する `Long[]` コンバーター</span><span class="sxs-lookup"><span data-stu-id="a0c8b-237">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="a0c8b-238">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="a0c8b-238">Additional resources</span></span>

* [<span data-ttu-id="a0c8b-239">System.string の概要</span><span class="sxs-lookup"><span data-stu-id="a0c8b-239">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="a0c8b-240">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a0c8b-240">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="a0c8b-241">方法: system.string を使用する</span><span class="sxs-lookup"><span data-stu-id="a0c8b-241">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="a0c8b-242">組み込みのコンバーターのソースコード</span><span class="sxs-lookup"><span data-stu-id="a0c8b-242">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="a0c8b-243">`System.Text.Json` のカスタムコンバーターに関連する GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="a0c8b-243">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="a0c8b-244">36639カスタムコンバーターの概要</span><span class="sxs-lookup"><span data-stu-id="a0c8b-244">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="a0c8b-245">38713オブジェクトへの逆シリアル化について</span><span class="sxs-lookup"><span data-stu-id="a0c8b-245">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="a0c8b-246">40120非文字列キー辞書について</span><span class="sxs-lookup"><span data-stu-id="a0c8b-246">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="a0c8b-247">37787ポリモーフィック逆シリアル化について</span><span class="sxs-lookup"><span data-stu-id="a0c8b-247">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)

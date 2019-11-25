---
title: '方法: DataContractJsonSerializer を使用する'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 354f0c58a83e07ff3180977311adf85ae306dd21
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976870"
---
# <a name="how-to-use-datacontractjsonserializer"></a><span data-ttu-id="faf41-102">DataContractJsonSerializer の使用方法</span><span class="sxs-lookup"><span data-stu-id="faf41-102">How to use DataContractJsonSerializer</span></span>

> [!NOTE]
> <span data-ttu-id="faf41-103">この記事では、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>について説明します。</span><span class="sxs-lookup"><span data-stu-id="faf41-103">This article is about <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="faf41-104">JSON のシリアル化と逆シリアル化を含むほとんどのシナリオでは、system.string[名前空間](../../../standard/serialization/system-text-json-overview.md)のツールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="faf41-104">For most scenarios that involve serializing and deserializing JSON, we recommend the tools in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span>

<span data-ttu-id="faf41-105">JSON (JavaScript Object Notation) は、クライアント ブラウザーと AJAX 対応の Web サービスとの間で、少量のデータを高速に交換できる効率的なデータ エンコード形式です。</span><span class="sxs-lookup"><span data-stu-id="faf41-105">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>

<span data-ttu-id="faf41-106">この記事では、.NET 型オブジェクトを JSON エンコードされたデータにシリアル化し、JSON 形式のデータを .NET 型のインスタンスに逆シリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="faf41-106">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="faf41-107">この例では、データコントラクトを使用して、ユーザー定義 `Person` 型のシリアル化と逆シリアル化を示し、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> を使用します。</span><span class="sxs-lookup"><span data-stu-id="faf41-107">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<span data-ttu-id="faf41-108">通常、AJAX 対応のエンドポイントで公開されるサービス操作でデータコントラクト型を使用する場合、JSON のシリアル化と逆シリアル化は、Windows Communication Foundation (WCF) によって自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="faf41-108">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="faf41-109">ただし、場合によっては、JSON データを直接操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faf41-109">However, in some cases you may need to work with JSON data directly.</span></span>

<span data-ttu-id="faf41-110">この記事は、 [DataContractJsonSerializer サンプル](../samples/json-serialization.md)を基にしています。</span><span class="sxs-lookup"><span data-stu-id="faf41-110">This article is based on the [DataContractJsonSerializer sample](../samples/json-serialization.md).</span></span>

## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="faf41-111">個人の種類のデータコントラクトを定義するには</span><span class="sxs-lookup"><span data-stu-id="faf41-111">To define the data contract for a Person type</span></span>

1. <span data-ttu-id="faf41-112">クラスに `Person` をアタッチし、シリアル化するメンバーに <xref:System.Runtime.Serialization.DataContractAttribute> 属性をアタッチすることで、<xref:System.Runtime.Serialization.DataMemberAttribute> のデータ コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="faf41-112">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="faf41-113">データコントラクトの詳細については、「[サービスコントラクトの設計](../designing-service-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf41-113">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>

    ```csharp
    [DataContract]
    internal class Person
    {
        [DataMember]
        internal string name;

        [DataMember]
        internal int age;
    }
    ```

## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="faf41-114">Person 型のインスタンスを JSON にシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="faf41-114">To serialize an instance of type Person to JSON</span></span>

> [!NOTE]
> <span data-ttu-id="faf41-115">サーバー上の送信応答のシリアル化中または他の何らかの理由でエラーが発生した場合、エラーとしてクライアントに返されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="faf41-115">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>

1. <span data-ttu-id="faf41-116">`Person` 型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="faf41-116">Create an instance of the `Person` type.</span></span>

    ```csharp
    var p = new Person();
    p.name = "John";
    p.age = 42;
    ```

2. <span data-ttu-id="faf41-117"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>を使用して、`Person` オブジェクトをメモリストリームにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="faf41-117">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

    ```csharp
    var stream1 = new MemoryStream();
    var ser = new DataContractJsonSerializer(typeof(Person));
    ```

3. <span data-ttu-id="faf41-118">JSON データをストリームに書き込むには、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="faf41-118">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>

    ```csharp
    ser.WriteObject(stream1, p);
    ```

4. <span data-ttu-id="faf41-119">JSON の出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="faf41-119">Show the JSON output.</span></span>

    ```csharp
    stream1.Position = 0;
    var sr = new StreamReader(stream1);
    Console.Write("JSON form of Person object: ");
    Console.WriteLine(sr.ReadToEnd());
    ```

## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="faf41-120">JSON から Person 型のインスタンスに逆シリアル化するには</span><span class="sxs-lookup"><span data-stu-id="faf41-120">To deserialize an instance of type Person from JSON</span></span>

1. <span data-ttu-id="faf41-121">`Person` の <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> メソッドを使用して、JSON エンコードされたデータを <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> の新しいインスタンスに逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="faf41-121">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

    ```csharp
    stream1.Position = 0;
    var p2 = (Person)ser.ReadObject(stream1);
    ```

2. <span data-ttu-id="faf41-122">結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="faf41-122">Show the results.</span></span>

    ```csharp
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");
    ```

## <a name="example"></a><span data-ttu-id="faf41-123">例</span><span class="sxs-lookup"><span data-stu-id="faf41-123">Example</span></span>

```csharp
// Create a User object and serialize it to a JSON stream.
public static string WriteFromObject()
{
    // Create User object.
    var user = new User("Bob", 42);

    // Create a stream to serialize the object to.
    var ms = new MemoryStream();

    // Serializer the User object to the stream.
    var ser = new DataContractJsonSerializer(typeof(User));
    ser.WriteObject(ms, user);
    byte[] json = ms.ToArray();
    ms.Close();
    return Encoding.UTF8.GetString(json, 0, json.Length);
}

// Deserialize a JSON stream to a User object.
public static User ReadToObject(string json)
{
    var deserializedUser = new User();
    var ms = new MemoryStream(Encoding.UTF8.GetBytes(json));
    var ser = new DataContractJsonSerializer(deserializedUser.GetType());
    deserializedUser = ser.ReadObject(ms) as User;
    ms.Close();
    return deserializedUser;
}
```

> [!NOTE]
> <span data-ttu-id="faf41-124">JSON シリアライザーは、次のサンプル コードに示すように、データ コントラクターの複数のメンバーが同じ名前である場合、シリアル化例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="faf41-124">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>

```csharp
[DataContract]
public class TestDuplicateDataBase
{
    [DataMember]
    public int field1 = 123;
}

[DataContract]
public class TestDuplicateDataDerived : TestDuplicateDataBase
{
    [DataMember]
    public new int field1 = 999;
}
```

## <a name="see-also"></a><span data-ttu-id="faf41-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="faf41-125">See also</span></span>

- [<span data-ttu-id="faf41-126">.NET での JSON のシリアル化</span><span class="sxs-lookup"><span data-stu-id="faf41-126">JSON serialization in .NET</span></span>](../../../standard/serialization/system-text-json-overview.md)

---
title: '方法: JSON データをシリアル化および逆シリアル化する'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 7edce66a23021fa03a6f98b3b847a5b671c17124
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336955"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="39afa-102">方法: および JSON データを逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="39afa-102">How to: Serialize and deserialize JSON data</span></span>
<span data-ttu-id="39afa-103">JSON (JavaScript Object Notation) は、クライアント ブラウザーと AJAX 対応の Web サービスとの間で、少量のデータを高速に交換できる効率的なデータ エンコード形式です。</span><span class="sxs-lookup"><span data-stu-id="39afa-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="39afa-104">この記事では、JSON でエンコードされたデータに .NET 型のオブジェクトをシリアル化して、JSON 形式でデータをシリアル化の .NET 型のインスタンスに戻す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="39afa-104">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="39afa-105">この例では、データ コントラクトを使用して、シリアル化と逆シリアル化ユーザー定義の方法を示します`Person`使用して型<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="39afa-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
 <span data-ttu-id="39afa-106">通常、JSON のシリアル化および逆シリアル化は自動的に処理 Windows Communication Foundation (WCF) によって AJAX 対応エンドポイント経由で公開されているサービス操作でデータ コントラクト型を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="39afa-106">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="39afa-107">ただし、場合によっては、JSON データを直接操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39afa-107">However, in some cases you may need to work with JSON data directly.</span></span>   
  
> [!NOTE]
>  <span data-ttu-id="39afa-108">サーバーまたは他の何らかの送信応答のシリアル化中にエラーが発生した場合に返されないことが取得をクライアントにエラーとして。</span><span class="sxs-lookup"><span data-stu-id="39afa-108">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="39afa-109">この記事がに基づいて、 [JSON のシリアル化](../samples/json-serialization.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="39afa-109">This article is based on the [JSON serialization](../samples/json-serialization.md) sample.</span></span>  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="39afa-110">Person 型のデータ コントラクトを定義するには</span><span class="sxs-lookup"><span data-stu-id="39afa-110">To define the data contract for a Person type</span></span> 
  
1. <span data-ttu-id="39afa-111">クラスに `Person` をアタッチし、シリアル化するメンバーに <xref:System.Runtime.Serialization.DataContractAttribute> 属性をアタッチすることで、<xref:System.Runtime.Serialization.DataMemberAttribute> のデータ コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="39afa-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="39afa-112">データ コントラクトの詳細については、次を参照してください。[サービス コントラクトの設計](../designing-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="39afa-112">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>  
  
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
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="39afa-113">Person 型のインスタンスを JSON にシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="39afa-113">To serialize an instance of type Person to JSON</span></span>  
  
1. <span data-ttu-id="39afa-114">`Person` 型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="39afa-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. <span data-ttu-id="39afa-115">シリアル化、`Person`オブジェクトをメモリ ストリームを使用して、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="39afa-115">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. <span data-ttu-id="39afa-116">JSON データをストリームに書き込むには、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="39afa-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. <span data-ttu-id="39afa-117">JSON の出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="39afa-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="39afa-118">JSON から Person 型のインスタンスに逆シリアル化するには</span><span class="sxs-lookup"><span data-stu-id="39afa-118">To deserialize an instance of type Person from JSON</span></span>  
  
1. <span data-ttu-id="39afa-119">`Person` の <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> メソッドを使用して、JSON エンコードされたデータを <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> の新しいインスタンスに逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="39afa-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2. <span data-ttu-id="39afa-120">結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="39afa-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="39afa-121">例</span><span class="sxs-lookup"><span data-stu-id="39afa-121">Example</span></span>  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="39afa-122">JSON シリアライザーは、次のサンプル コードに示すように、データ コントラクターの複数のメンバーが同じ名前である場合、シリアル化例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="39afa-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39afa-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="39afa-123">See also</span></span>

- [<span data-ttu-id="39afa-124">スタンドアロン JSON のシリアル化</span><span class="sxs-lookup"><span data-stu-id="39afa-124">Stand-alone JSON serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="39afa-125">JSON のサポートおよびその他のデータ転送の形式</span><span class="sxs-lookup"><span data-stu-id="39afa-125">Support for JSON and other data transfer formats</span></span>](support-for-json-and-other-data-transfer-formats.md)

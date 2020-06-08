---
title: '方法: オブジェクトを SOAP エンコード済み XML ストリームとしてシリアル化する'
description: オブジェクトを SOAP エンコード済み XML ストリームとしてシリアル化する方法について説明します。 XmlSerializer クラスは、クラスをシリアル化し、エンコード済みの SOAP メッセージを生成するために使用できます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: 1d38c4e334439ef41b4d4429e52cff04c6463573
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291566"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="b8c50-104">方法: オブジェクトを SOAP エンコード済み XML ストリームとしてシリアル化する</span><span class="sxs-lookup"><span data-stu-id="b8c50-104">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="b8c50-105">SOAP メッセージは XML を使用して作成されるため、<xref:System.Xml.Serialization.XmlSerializer> クラスを使用してクラスをシリアル化し、エンコード済みの SOAP メッセージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c50-105">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="b8c50-106">生成される XML は、[W3C (World Wide Web Consortium) のドキュメント『Simple Object Access Protocol (SOAP) 1.1』のセクション 5](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512) に準拠します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-106">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="b8c50-107">SOAP メッセージを使用して通信を行う XML Web サービスを作成する場合、特殊な SOAP 属性のセットをクラスやクラスのメンバーに適用することで、生成される XML ストリームをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b8c50-107">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="b8c50-108">属性の一覧については、「[Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c50-108">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="b8c50-109">オブジェクトを SOAP エンコード済み XML ストリームとしてシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="b8c50-109">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="b8c50-110">[XML スキーマ定義ツール (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md) を使用して、クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-110">Create the class using the [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="b8c50-111">`System.Xml.Serialization` の特別な属性を 1 つ以上適用します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-111">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="b8c50-112">「エンコード済み SOAP シリアル化を制御する属性」の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c50-112">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="b8c50-113">新しい `XmlTypeMapping` を作成し、シリアル化されるクラスの型を使用して `SoapReflectionImporter` メソッドを呼び出して、`ImportTypeMapping` を作成します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-113">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="b8c50-114">`ImportTypeMapping` クラスの `SoapReflectionImporter` メソッドを呼び出して `XmlTypeMapping` を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-114">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4. <span data-ttu-id="b8c50-115">`XmlSerializer` を `XmlTypeMapping` コンストラクターに渡して、<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-115">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="b8c50-116">`Serialize` メソッドまたは `Deserialize` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b8c50-116">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8c50-117">例</span><span class="sxs-lookup"><span data-stu-id="b8c50-117">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8c50-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8c50-118">See also</span></span>

- [<span data-ttu-id="b8c50-119">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="b8c50-119">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="b8c50-120">エンコード済み SOAP シリアル化を制御する属性</span><span class="sxs-lookup"><span data-stu-id="b8c50-120">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="b8c50-121">XML Web サービスを使用した XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="b8c50-121">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="b8c50-122">方法: オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="b8c50-122">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="b8c50-123">方法: オブジェクトを逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="b8c50-123">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="b8c50-124">方法: SOAP エンコード済み XML シリアル化をオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="b8c50-124">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)

---
title: '方法 : オブジェクトをシリアル化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: 3e24d890d47747c51086214530073fc551321079
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159885"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="3cb6f-102">方法 : オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="3cb6f-102">How to: Serialize an Object</span></span>
<span data-ttu-id="3cb6f-103">オブジェクトをシリアル化するには、まず、シリアル化の対象となるオブジェクトを作成し、パブリック プロパティとパブリック フィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="3cb6f-104">この処理を行うには、転送形式、つまり XML ストリームをストリームとファイルのいずれとして格納するかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="3cb6f-105">たとえば、XML ストリームを永続的な形式で保存する必要がある場合は、<xref:System.IO.FileStream> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cb6f-106">XML シリアル化の例については、「[Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="3cb6f-107">オブジェクトをシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="3cb6f-107">To serialize an object</span></span>  
  
1. <span data-ttu-id="3cb6f-108">オブジェクトを作成し、パブリック フィールドとパブリック プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-108">Create the object and set its public fields and properties.</span></span>  
  
2. <span data-ttu-id="3cb6f-109">そのオブジェクトの型を使用して、<xref:System.Xml.Serialization.XmlSerializer> を構築します。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="3cb6f-110">詳細については、<xref:System.Xml.Serialization.XmlSerializer> クラスのコンストラクターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3. <span data-ttu-id="3cb6f-111"><xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> メソッドを呼び出して、オブジェクトのパブリック プロパティとパブリック フィールドを XML ストリーム形式またはファイル形式のいずれかで生成します。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="3cb6f-112">ファイルを作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3cb6f-112">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3cb6f-113">参照</span><span class="sxs-lookup"><span data-stu-id="3cb6f-113">See also</span></span>

- [<span data-ttu-id="3cb6f-114">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="3cb6f-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="3cb6f-115">方法 : オブジェクトを逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="3cb6f-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

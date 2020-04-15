---
title: '方法: XML スキーマ定義ツールを使用してクラスと XML スキーマ ドキュメントを生成する'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 2bbdced0f984b653a58afba9685683e8c0891271
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389794"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="bde38-102">方法: XML スキーマ定義ツールを使用してクラスと XML スキーマ ドキュメントを生成する</span><span class="sxs-lookup"><span data-stu-id="bde38-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="bde38-103">XML スキーマ定義ツール (Xsd.exe) を使用して、クラスを説明する XML スキーマを生成したり、XML スキーマで定義されるクラスを生成したりできます。</span><span class="sxs-lookup"><span data-stu-id="bde38-103">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="bde38-104">次の手順では、これらの操作の実行方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bde38-104">The following procedures show how to perform these operations.</span></span>

<span data-ttu-id="bde38-105">XML スキーマ定義ツール (Xsd.exe) は、通常、次のパスにあります。</span><span class="sxs-lookup"><span data-stu-id="bde38-105">The XML Schema Definition tool (Xsd.exe) usually can be found in the following path:\</span></span>
<span data-ttu-id="bde38-106">_C:\\プログラム\\ファイル (x86)\\マイクロソフト\\SDK\\ウィンドウ\\{バージョン} ビン NETFX {バージョン} ツール\\_</span><span class="sxs-lookup"><span data-stu-id="bde38-106">_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span></span>

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="bde38-107">特定のスキーマに準拠するクラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="bde38-107">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="bde38-108">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="bde38-108">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="bde38-109">XML スキーマ定義ツールに XML スキーマを引数として渡します。XML スキーマ定義ツールは、次のように XML スキーマに正確に一致するクラスのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde38-109">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="bde38-110">ツールは、2001 年 3 月 16 日付けの World Wide Web Consortium XML 仕様を参照するスキーマのみを処理できます。</span><span class="sxs-lookup"><span data-stu-id="bde38-110">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="bde38-111">つまり、XML スキーマ名前空間は、次の例http://www.w3.org/2001/XMLSchemaに示すように " " にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bde38-111">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. <span data-ttu-id="bde38-112">必要に応じて、クラスのメソッド、プロパティ、またはフィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="bde38-112">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="bde38-113">属性によるクラスの変更の詳細については、「[属性を使用した XML シリアル化の制御](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)」と「[エンコード済み SOAP シリアル化を制御する属性](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bde38-113">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="bde38-114">クラスのインスタンスがシリアル化されるときに生成される XML ストリームのスキーマを調べることは、さまざまな場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bde38-114">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="bde38-115">たとえば、他のユーザーが使用できるようにスキーマを公開したり、準拠しようとしているスキーマと自分のスキーマを比較したりできます。</span><span class="sxs-lookup"><span data-stu-id="bde38-115">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="bde38-116">クラスのセットから XML スキーマ ドキュメントを生成するには</span><span class="sxs-lookup"><span data-stu-id="bde38-116">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="bde38-117">クラスを DLL にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="bde38-117">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="bde38-118">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="bde38-118">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="bde38-119">次の例に示すように、DLL を引数として Xsd.exe に渡します。</span><span class="sxs-lookup"><span data-stu-id="bde38-119">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="bde38-120">スキーマが、"schema0.xsd" という名前から順に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="bde38-120">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde38-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bde38-121">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="bde38-122">XML スキーマ定義ツールと XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="bde38-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="bde38-123">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="bde38-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="bde38-124">XML スキーマ定義ツール (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="bde38-124">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="bde38-125">方法: オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="bde38-125">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="bde38-126">方法: オブジェクトを逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="bde38-126">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

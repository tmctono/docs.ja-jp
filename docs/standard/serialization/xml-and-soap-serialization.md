---
title: XML シリアル化および SOAP シリアル化
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: d9dc68d8e7eced031af404aaec20784573c9930a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028240"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="00f2b-102">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="00f2b-102">XML and SOAP Serialization</span></span>

<span data-ttu-id="00f2b-103">XML シリアル化とは、オブジェクトのパブリック フィールドやパブリック プロパティ、またはメソッドのパラメーターや戻り値を、特定の XML スキーマ定義言語 (XSD: XML Schema Definition Language) ドキュメントに準拠する XML ストリームに変換 (シリアル化) する処理です。</span><span class="sxs-lookup"><span data-stu-id="00f2b-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="00f2b-104">XML シリアル化によって、パブリック プロパティおよびパブリック フィールドを含むクラスの型が厳密に指定され、それらのパブリック メンバーは格納または転送できるようにシリアル形式 (この場合は XML) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="00f2b-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="00f2b-105">XML はオープン標準であるため、XML ストリームは、プラットフォームに関係なく、必要に応じて任意のアプリケーションで処理できます。</span><span class="sxs-lookup"><span data-stu-id="00f2b-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="00f2b-106">たとえば、ASP.NET を使用して作成された XML Web サービスは、<xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、インターネット全体またはイントラネット上の XML Web サービス アプリケーション間でデータを受け渡しする XML ストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="00f2b-107">一方、逆シリアル化は、このような XML ストリームからデータを取得して、元のオブジェクトを再構築します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="00f2b-108">XML シリアル化を使用して、SOAP 仕様に準拠する XML ストリームにオブジェクトをシリアル化することもできます。</span><span class="sxs-lookup"><span data-stu-id="00f2b-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="00f2b-109">SOAP は、XML を使用してプロシージャ呼び出しを転送するために特別にデザインされた、XML に基づくプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="00f2b-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="00f2b-110">オブジェクトをシリアル化または逆シリアル化するには、<xref:System.Xml.Serialization.XmlSerializer> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="00f2b-111">また、シリアル化する対象のクラスを作成するには、XML スキーマ定義ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="00f2b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="00f2b-112">In This Section</span></span>

[<span data-ttu-id="00f2b-113">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="00f2b-113">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)  
<span data-ttu-id="00f2b-114">シリアル化、特に XML シリアル化の一般的な定義を示します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-114">Provides a general definition of serialization, particularly XML serialization.</span></span>

[<span data-ttu-id="00f2b-115">方法: オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-115">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)  
<span data-ttu-id="00f2b-116">オブジェクトをシリアル化するための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-116">Provides step-by-step instructions for serializing an object.</span></span>

[<span data-ttu-id="00f2b-117">方法: オブジェクトを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)  
<span data-ttu-id="00f2b-118">オブジェクトを逆シリアル化するための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-118">Provides step-by-step instructions for deserializing an object.</span></span>

[<span data-ttu-id="00f2b-119">XML シリアル化の例</span><span class="sxs-lookup"><span data-stu-id="00f2b-119">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)  
<span data-ttu-id="00f2b-120">XML シリアル化の基本事項を示す例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-120">Provides examples that demonstrate the basics of XML serialization.</span></span>

[<span data-ttu-id="00f2b-121">XML スキーマ定義ツールと XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="00f2b-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)  
<span data-ttu-id="00f2b-122">XML スキーマ定義ツールを使用して、特定の XML スキーマ定義言語 (XSD) スキーマに準拠するクラスを作成したり、.dll ファイルから XML スキーマを生成したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>

[<span data-ttu-id="00f2b-123">属性を使用した XML シリアル化の制御</span><span class="sxs-lookup"><span data-stu-id="00f2b-123">Controlling XML Serialization Using Attributes</span></span>](controlling-xml-serialization-using-attributes.md)  
<span data-ttu-id="00f2b-124">属性を使用してシリアル化を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-124">Describes how to control serialization by using attributes.</span></span>

[<span data-ttu-id="00f2b-125">XML シリアル化を制御する属性</span><span class="sxs-lookup"><span data-stu-id="00f2b-125">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)  
<span data-ttu-id="00f2b-126">XML シリアル化の制御に使用する属性を示します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-126">Lists the attributes that are used to control XML serialization.</span></span>

[<span data-ttu-id="00f2b-127">方法: XML Stream の代替要素名を指定します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
<span data-ttu-id="00f2b-128">シリアル化のオーバーライドにより、複数の XML ストリームを生成する方法を示す高度なシナリオを紹介します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>

[<span data-ttu-id="00f2b-129">方法: 派生クラスのシリアル化を制御</span><span class="sxs-lookup"><span data-stu-id="00f2b-129">How to: Control Serialization of Derived Classes</span></span>](how-to-control-serialization-of-derived-classes.md)  
<span data-ttu-id="00f2b-130">派生クラスのシリアル化の制御方法を示す例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-130">Provides an example of how to control the serialization of derived classes.</span></span>

[<span data-ttu-id="00f2b-131">方法: XML 要素および XML 属性の名前を修飾します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-131">How to: Qualify XML Element and XML Attribute Names</span></span>](how-to-qualify-xml-element-and-xml-attribute-names.md)  
<span data-ttu-id="00f2b-132">XML ストリームでの XML 名前空間の使用方法を定義および制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>

[<span data-ttu-id="00f2b-133">XML Web サービスを使用した XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="00f2b-133">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)  
<span data-ttu-id="00f2b-134">XML Web サービスでの XML シリアル化の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-134">Explains how XML serialization is used in XML Web services.</span></span>

[<span data-ttu-id="00f2b-135">方法: SOAP エンコード済み XML Stream としてオブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
<span data-ttu-id="00f2b-136">使用する方法について説明します、 <xref:System.Xml.Serialization.XmlSerializer> World Wide Web Consortium (W3C) ドキュメントのセクション 5 に準拠しているエンコード済みの SOAP XML ストリームを作成するクラス[簡易オブジェクト アクセス プロトコル (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span></span>

[<span data-ttu-id="00f2b-137">方法: SOAP エンコード済み XML シリアル化をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="00f2b-137">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)  
<span data-ttu-id="00f2b-138">SOAP メッセージとしてのオブジェクトの XML シリアル化をオーバーライドするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>

[<span data-ttu-id="00f2b-139">エンコード済み SOAP シリアル化を制御する属性</span><span class="sxs-lookup"><span data-stu-id="00f2b-139">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)  
<span data-ttu-id="00f2b-140">SOAP エンコード済みのシリアル化の制御に使用する属性を示します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>

[<span data-ttu-id="00f2b-141">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-141">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)  
<span data-ttu-id="00f2b-142">XML シリアル化を制御する最上位の構成要素です。</span><span class="sxs-lookup"><span data-stu-id="00f2b-142">The top-level configuration element for controlling XML serialization.</span></span>

[<span data-ttu-id="00f2b-143">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-143">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)  
<span data-ttu-id="00f2b-144"><xref:System.DateTime> オブジェクトのシリアル化モードを制御します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>

[<span data-ttu-id="00f2b-145">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-145">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)  
<span data-ttu-id="00f2b-146"><xref:System.Xml.Serialization.XmlSchemaImporter> クラスによって使用される型を含みます。</span><span class="sxs-lookup"><span data-stu-id="00f2b-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

[<span data-ttu-id="00f2b-147">\<追加 > 要素の\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="00f2b-147">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)  
<span data-ttu-id="00f2b-148"><xref:System.Xml.Serialization.XmlSchemaImporter> クラスによって使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

## <a name="related-sections"></a><span data-ttu-id="00f2b-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="00f2b-149">Related Sections</span></span>

<span data-ttu-id="00f2b-150">[ASP.NET と XML Web サービス クライアントを使用して作成した XML Web サービス](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="00f2b-150">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>  
<span data-ttu-id="00f2b-151">ASP.NET を使用した XML Web サービスのプログラミング方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-151">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="00f2b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="00f2b-152">See also</span></span>

- [<span data-ttu-id="00f2b-153">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="00f2b-153">Binary Serialization</span></span>](binary-serialization.md)

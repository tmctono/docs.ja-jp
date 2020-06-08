---
title: エンコード済み SOAP シリアル化を制御する属性
description: この記事では、SOAP 仕様に準拠するために必要な System.Xml.Serialization 名前空間で指定されている特殊な属性のセットの一覧を示します。
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: d9a4631189d348c02ab36054257a54c9c4673018
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289669"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="d3df7-103">エンコード済み SOAP シリアル化を制御する属性</span><span class="sxs-lookup"><span data-stu-id="d3df7-103">Attributes That Control Encoded SOAP Serialization</span></span>

<span data-ttu-id="d3df7-104">World Wide Web コンソーシアム (W3C) のドキュメント『[Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)』には、SOAP パラメーターのエンコード方法について説明したオプションのセクション (セクション 5) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3df7-104">The World Wide Web Consortium (W3C) document named [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="d3df7-105">このセクション 5 の仕様に準拠するには、<xref:System.Xml.Serialization> 名前空間で指定されている特殊な属性セットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3df7-105">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="d3df7-106">これらの属性をクラスやクラスのメンバーに適宜適用し、<xref:System.Xml.Serialization.XmlSerializer> を使用して、クラスのインスタンスをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-106">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>

<span data-ttu-id="d3df7-107">これらの属性、およびその適用対象と機能を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-107">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="d3df7-108">これらの属性を使用して XML シリアル化を制御する方法の詳細については、「[方法: オブジェクトを SOAP エンコード済み XML ストリームとしてシリアル化する](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)」と「[方法: SOAP エンコード済み XML シリアル化をオーバーライドする](how-to-override-encoded-soap-xml-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3df7-108">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](how-to-override-encoded-soap-xml-serialization.md).</span></span>

<span data-ttu-id="d3df7-109">属性の詳細については、「[属性](../attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3df7-109">For more information about attributes, see [Attributes](../attributes/index.md).</span></span>

|<span data-ttu-id="d3df7-110">属性</span><span class="sxs-lookup"><span data-stu-id="d3df7-110">Attribute</span></span>|<span data-ttu-id="d3df7-111">対象</span><span class="sxs-lookup"><span data-stu-id="d3df7-111">Applies to</span></span>|<span data-ttu-id="d3df7-112">指定内容</span><span class="sxs-lookup"><span data-stu-id="d3df7-112">Specifies</span></span>|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="d3df7-113">パブリック フィールド、パブリック プロパティ、パブリック パラメーター、または戻り値</span><span class="sxs-lookup"><span data-stu-id="d3df7-113">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="d3df7-114">クラス メンバーを XML 属性としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-114">The class member will be serialized as an XML attribute.</span></span>|
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="d3df7-115">パブリック フィールド、パブリック プロパティ、パブリック パラメーター、または戻り値</span><span class="sxs-lookup"><span data-stu-id="d3df7-115">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="d3df7-116">クラスを XML 要素としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-116">The class will be serialized as an XML element.</span></span>|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="d3df7-117">列挙体識別子であるパブリック フィールド</span><span class="sxs-lookup"><span data-stu-id="d3df7-117">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="d3df7-118">列挙体のメンバーの要素名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-118">The element name of an enumeration member.</span></span>|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="d3df7-119">パブリック プロパティとパブリック フィールド</span><span class="sxs-lookup"><span data-stu-id="d3df7-119">Public properties and fields.</span></span>|<span data-ttu-id="d3df7-120">クラスのシリアル化時に、そのクラスに含まれているプロパティまたはフィールドを無視します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-120">The property or field should be ignored when the containing class is serialized.</span></span>|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="d3df7-121">パブリック派生クラス宣言、およびパブリック メソッド (Web サービス記述言語 (WSDL: Web Service Description Language) ドキュメント用)</span><span class="sxs-lookup"><span data-stu-id="d3df7-121">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="d3df7-122">シリアル化時に認識されるように、スキーマの生成時にその型を対象に含めます。</span><span class="sxs-lookup"><span data-stu-id="d3df7-122">The type should be included when generating schemas (to be recognized when serialized).</span></span>|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="d3df7-123">パブリック クラス宣言</span><span class="sxs-lookup"><span data-stu-id="d3df7-123">Public class declarations.</span></span>|<span data-ttu-id="d3df7-124">クラスを XML 型としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="d3df7-124">The class should be serialized as an XML type.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d3df7-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3df7-125">See also</span></span>

- [<span data-ttu-id="d3df7-126">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="d3df7-126">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="d3df7-127">方法: オブジェクトを SOAP エンコード済み XML ストリームとしてシリアル化する</span><span class="sxs-lookup"><span data-stu-id="d3df7-127">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [<span data-ttu-id="d3df7-128">方法: SOAP エンコード済み XML シリアル化をオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="d3df7-128">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
- [<span data-ttu-id="d3df7-129">属性</span><span class="sxs-lookup"><span data-stu-id="d3df7-129">Attributes</span></span>](../attributes/index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="d3df7-130">方法: オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="d3df7-130">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="d3df7-131">方法: オブジェクトを逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="d3df7-131">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)

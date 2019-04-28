---
title: エンコード済み SOAP シリアル化を制御する属性
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 2961d9abc6c32e78b5a61e8f2bbea5cfcf6677bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794941"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="ddaff-102">エンコード済み SOAP シリアル化を制御する属性</span><span class="sxs-lookup"><span data-stu-id="ddaff-102">Attributes That Control Encoded SOAP Serialization</span></span>

<span data-ttu-id="ddaff-103">という名前の World Wide Web Consortium (W3C) ドキュメント[簡易オブジェクト アクセス プロトコル (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) SOAP パラメーターのエンコード方法について説明する省略可能なセクション (セクション 5) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ddaff-103">The World Wide Web Consortium (W3C) document named [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="ddaff-104">このセクション 5 の仕様に準拠するには、<xref:System.Xml.Serialization> 名前空間で指定されている特殊な属性セットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddaff-104">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="ddaff-105">これらの属性をクラスやクラスのメンバーに適宜適用し、<xref:System.Xml.Serialization.XmlSerializer> を使用して、クラスのインスタンスをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-105">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>

<span data-ttu-id="ddaff-106">これらの属性、およびその適用対象と機能を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-106">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="ddaff-107">詳細については、XML シリアル化を制御するこれらの属性を使用して、次を参照してください。[方法。Serialize an Object as SOAP エンコード済み XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)と[方法。SOAP エンコード済み XML シリアル化をオーバーライド](how-to-override-encoded-soap-xml-serialization.md)します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-107">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](how-to-override-encoded-soap-xml-serialization.md).</span></span>

<span data-ttu-id="ddaff-108">属性の詳細については、「[属性](../../../docs/standard/attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddaff-108">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>

|<span data-ttu-id="ddaff-109">属性</span><span class="sxs-lookup"><span data-stu-id="ddaff-109">Attribute</span></span>|<span data-ttu-id="ddaff-110">対象</span><span class="sxs-lookup"><span data-stu-id="ddaff-110">Applies to</span></span>|<span data-ttu-id="ddaff-111">指定内容</span><span class="sxs-lookup"><span data-stu-id="ddaff-111">Specifies</span></span>|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="ddaff-112">パブリック フィールド、パブリック プロパティ、パブリック パラメーター、または戻り値</span><span class="sxs-lookup"><span data-stu-id="ddaff-112">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="ddaff-113">クラス メンバーを XML 属性としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-113">The class member will be serialized as an XML attribute.</span></span>|
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="ddaff-114">パブリック フィールド、パブリック プロパティ、パブリック パラメーター、または戻り値</span><span class="sxs-lookup"><span data-stu-id="ddaff-114">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="ddaff-115">クラスを XML 要素としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-115">The class will be serialized as an XML element.</span></span>|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="ddaff-116">列挙体識別子であるパブリック フィールド</span><span class="sxs-lookup"><span data-stu-id="ddaff-116">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="ddaff-117">列挙体のメンバーの要素名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-117">The element name of an enumeration member.</span></span>|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="ddaff-118">パブリック プロパティとパブリック フィールド</span><span class="sxs-lookup"><span data-stu-id="ddaff-118">Public properties and fields.</span></span>|<span data-ttu-id="ddaff-119">クラスのシリアル化時に、そのクラスに含まれているプロパティまたはフィールドを無視します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-119">The property or field should be ignored when the containing class is serialized.</span></span>|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="ddaff-120">パブリック派生クラス宣言、およびパブリック メソッド (Web サービス記述言語 (WSDL: Web Service Description Language) ドキュメント用)</span><span class="sxs-lookup"><span data-stu-id="ddaff-120">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="ddaff-121">シリアル化時に認識されるように、スキーマの生成時にその型を対象に含めます。</span><span class="sxs-lookup"><span data-stu-id="ddaff-121">The type should be included when generating schemas (to be recognized when serialized).</span></span>|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="ddaff-122">パブリック クラス宣言</span><span class="sxs-lookup"><span data-stu-id="ddaff-122">Public class declarations.</span></span>|<span data-ttu-id="ddaff-123">クラスを XML 型としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-123">The class should be serialized as an XML type.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ddaff-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddaff-124">See also</span></span>

- [<span data-ttu-id="ddaff-125">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="ddaff-125">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="ddaff-126">方法: SOAP エンコード済み XML Stream としてオブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-126">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [<span data-ttu-id="ddaff-127">方法: SOAP エンコード済み XML シリアル化をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ddaff-127">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
- [<span data-ttu-id="ddaff-128">属性</span><span class="sxs-lookup"><span data-stu-id="ddaff-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="ddaff-129">方法: オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-129">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="ddaff-130">方法: オブジェクトを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ddaff-130">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)

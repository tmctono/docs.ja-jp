---
title: XML シリアル化および SOAP シリアル化
description: この概要では、SOAP 仕様に準拠する XML ストリームにオブジェクトをシリアル化することもできる XML シリアル化について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: 6b7d6f59694a28207758fa7772781eed073917e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379541"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="92d0f-103">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="92d0f-103">XML and SOAP serialization</span></span>

<span data-ttu-id="92d0f-104">XML シリアル化とは、オブジェクトのパブリック フィールドやパブリック プロパティ、およびメソッドのパラメーターや戻り値を、特定の XML スキーマ定義言語 (XSD: XML Schema Definition Language) ドキュメントに準拠する XML ストリームに変換 (シリアル化) する処理です。</span><span class="sxs-lookup"><span data-stu-id="92d0f-104">XML serialization converts (serializes) the public fields and properties of an object, and the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="92d0f-105">XML シリアル化によって、パブリック プロパティおよびパブリック フィールドを含むクラスの型が厳密に指定され、それらのパブリック メンバーは格納または転送できるようにシリアル形式 (この場合は XML) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="92d0f-105">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="92d0f-106">XML はオープン標準であるため、XML ストリームは、プラットフォームに関係なく、必要に応じて任意のアプリケーションで処理できます。</span><span class="sxs-lookup"><span data-stu-id="92d0f-106">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="92d0f-107">たとえば、ASP.NET を使用して作成された XML Web サービスは、<xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、インターネット全体またはイントラネット上の XML Web サービス アプリケーション間でデータを受け渡しする XML ストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="92d0f-107">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="92d0f-108">一方、逆シリアル化は、このような XML ストリームからデータを取得して、元のオブジェクトを再構築します。</span><span class="sxs-lookup"><span data-stu-id="92d0f-108">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="92d0f-109">XML シリアル化を使用して、SOAP 仕様に準拠する XML ストリームにオブジェクトをシリアル化することもできます。</span><span class="sxs-lookup"><span data-stu-id="92d0f-109">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="92d0f-110">SOAP は、XML を使用してプロシージャ呼び出しを転送するために特別にデザインされた、XML に基づくプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="92d0f-110">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="92d0f-111">オブジェクトをシリアル化または逆シリアル化するには、<xref:System.Xml.Serialization.XmlSerializer> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d0f-111">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="92d0f-112">また、シリアル化する対象のクラスを作成するには、XML スキーマ定義ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d0f-112">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="92d0f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d0f-113">See also</span></span>

- [<span data-ttu-id="92d0f-114">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="92d0f-114">Binary Serialization</span></span>](binary-serialization.md)
- <span data-ttu-id="92d0f-115">[ASP.NET と XML Web サービス クライアントを使用して作成した XML Web サービス](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="92d0f-115">[XML Web Services created using ASP.NET and XML Web Service clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>

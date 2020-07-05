---
title: シリアル化 - .NET
description: この記事では、バイナリ シリアル化、XML および SOAP シリアル化、JSON シリアル化など、.NET シリアル化テクノロジに関する情報を提供します。
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "85840381"
---
# <a name="serialization-in-net"></a><span data-ttu-id="def3d-103">.NET でのシリアル化</span><span class="sxs-lookup"><span data-stu-id="def3d-103">Serialization in .NET</span></span>

<span data-ttu-id="def3d-104">シリアル化とは、オブジェクトの状態を永続化または転送できる形式に変換するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="def3d-104">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="def3d-105">シリアル化を補完するプロセスとして、ストリームをオブジェクトに変換する逆シリアル化があります。</span><span class="sxs-lookup"><span data-stu-id="def3d-105">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="def3d-106">これらのプロセスを共に使用することで、データを格納および転送できます。</span><span class="sxs-lookup"><span data-stu-id="def3d-106">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="def3d-107">.NET では、次のシリアル化テクノロジが提供されています。</span><span class="sxs-lookup"><span data-stu-id="def3d-107">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="def3d-108">[バイナリ シリアル化](binary-serialization.md)では、型そのものが正確に維持されるため、アプリケーションを次回起動するまでの間、オブジェクトの状態を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="def3d-108">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="def3d-109">たとえば、クリップボードを出力先としてオブジェクトをシリアル化することによって、そのオブジェクトを異なるアプリケーション間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="def3d-109">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="def3d-110">オブジェクトをシリアル化して、ストリーム、ディスク、メモリ、ネットワーク上などに出力できます。</span><span class="sxs-lookup"><span data-stu-id="def3d-110">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="def3d-111">リモート処理では、シリアル化を使用して、コンピューター間やアプリケーション ドメイン間でオブジェクトを "値渡し" します。</span><span class="sxs-lookup"><span data-stu-id="def3d-111">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="def3d-112">[XML および SOAP シリアル化](xml-and-soap-serialization.md)では、パブリック プロパティとフィールドのみがシリアル化され、型そのものは維持されません。</span><span class="sxs-lookup"><span data-stu-id="def3d-112">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="def3d-113">これは、データを使用するアプリケーションに制限を加えずに、データを提供または処理する場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="def3d-113">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="def3d-114">XML はオープン標準であるため、Web 経由でデータを共有する場合には有用な選択肢となります。</span><span class="sxs-lookup"><span data-stu-id="def3d-114">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="def3d-115">SOAP も同様のオープン標準であるため、有用な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="def3d-115">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="def3d-116">[JSON シリアル化](system-text-json-overview.md)では、パブリック プロパティのみがシリアル化され、型そのものは維持されません。</span><span class="sxs-lookup"><span data-stu-id="def3d-116">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="def3d-117">JSON はオープン標準です。Web 経由でデータを共有する場合には有用な選択肢となります。</span><span class="sxs-lookup"><span data-stu-id="def3d-117">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="def3d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="def3d-118">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="def3d-119">オブジェクトのシリアル化と逆シリアル化に使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="def3d-119">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="def3d-120">オブジェクトを XML 形式のドキュメントまたはストリームにシリアル化するために使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="def3d-120">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="def3d-121">オブジェクトを JSON 形式のドキュメントまたはストリームにシリアル化するために使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="def3d-121">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>

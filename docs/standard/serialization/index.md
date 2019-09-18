---
title: シリアル化-.NET
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053344"
---
# <a name="serialization-in-net"></a><span data-ttu-id="ffb9b-102">.NET でのシリアル化</span><span class="sxs-lookup"><span data-stu-id="ffb9b-102">Serialization in .NET</span></span>

<span data-ttu-id="ffb9b-103">シリアル化とは、オブジェクトの状態を永続化または転送できる形式に変換するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="ffb9b-104">シリアル化を補完するプロセスとして、ストリームをオブジェクトに変換する逆シリアル化があります。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="ffb9b-105">これらのプロセスを一緒に使用することで、データを格納および転送できます。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-105">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="ffb9b-106">.NET には、次のシリアル化テクノロジがあります。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-106">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="ffb9b-107">[バイナリシリアル化](binary-serialization.md)は、型の忠実性を保持します。これは、アプリケーションの異なる呼び出し間でオブジェクトの状態を保持する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-107">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="ffb9b-108">たとえば、クリップボードを出力先としてオブジェクトをシリアル化することによって、そのオブジェクトを異なるアプリケーション間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="ffb9b-109">オブジェクトをシリアル化して、ストリーム、ディスク、メモリ、ネットワーク上などに出力できます。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="ffb9b-110">リモート処理では、シリアル化を使用して、コンピューター間やアプリケーション ドメイン間でオブジェクトを "値渡し" します。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="ffb9b-111">[XML シリアル化および SOAP シリアル化](xml-and-soap-serialization.md)では、パブリックプロパティとパブリックフィールドのみがシリアル化され、型の忠実性は維持されません。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-111">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="ffb9b-112">これは、データを使用するアプリケーションに制限を加えずに、データを提供または処理する場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="ffb9b-113">XML はオープン標準であるため、Web 経由でデータを共有する場合には有用な選択肢となります。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="ffb9b-114">SOAP も同様のオープン標準であるため、有用な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="ffb9b-115">[JSON シリアル化](system-text-json-overview.md)では、パブリックプロパティのみがシリアル化され、型の忠実性は維持されません。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-115">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="ffb9b-116">JSON は、web 経由でデータを共有するための魅力的な選択肢であるオープンスタンダードです。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-116">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="ffb9b-117">参照</span><span class="sxs-lookup"><span data-stu-id="ffb9b-117">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="ffb9b-118">オブジェクトのシリアル化と逆シリアル化に使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-118">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="ffb9b-119">オブジェクトを XML 形式のドキュメントまたはストリームにシリアル化するために使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-119">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="ffb9b-120">オブジェクトを JSON 形式のドキュメントまたはストリームにシリアル化するために使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ffb9b-120">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>

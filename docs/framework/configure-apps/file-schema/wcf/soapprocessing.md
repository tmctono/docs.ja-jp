---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 678b1f71ac15d3ad30df28cec5abbe403fb08c95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937057"
---
# <a name="soapprocessing"></a><span data-ttu-id="d5c35-101">\<soapProcessing ></span><span class="sxs-lookup"><span data-stu-id="d5c35-101">\<soapProcessing></span></span>

<span data-ttu-id="d5c35-102">異なるバインディングの種類およびメッセージ バージョンの間でメッセージのマーシャリングに使用されるクライアント エンドポイントの動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5c35-102">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="d5c35-103">**\<system.ServiceModel>**  </span><span class="sxs-lookup"><span data-stu-id="d5c35-103">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="d5c35-104">&nbsp;&nbsp; **\<動作 >**  </span><span class="sxs-lookup"><span data-stu-id="d5c35-104">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="d5c35-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<endpointBehaviors >**  </span><span class="sxs-lookup"><span data-stu-id="d5c35-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="d5c35-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<動作 >**  </span><span class="sxs-lookup"><span data-stu-id="d5c35-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="d5c35-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<soapProcessing >**</span><span class="sxs-lookup"><span data-stu-id="d5c35-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d5c35-108">構文</span><span class="sxs-lookup"><span data-stu-id="d5c35-108">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5c35-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d5c35-109">Attributes and elements</span></span>  
  
<span data-ttu-id="d5c35-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5c35-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5c35-111">属性</span><span class="sxs-lookup"><span data-stu-id="d5c35-111">Attributes</span></span>  
  
|                   | <span data-ttu-id="d5c35-112">説明</span><span class="sxs-lookup"><span data-stu-id="d5c35-112">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="d5c35-113">SOAP メッセージ バージョン間のメッセージをマーシャリングするかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="d5c35-113">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d5c35-114">子要素</span><span class="sxs-lookup"><span data-stu-id="d5c35-114">Child elements</span></span>

<span data-ttu-id="d5c35-115">なし</span><span class="sxs-lookup"><span data-stu-id="d5c35-115">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d5c35-116">親要素</span><span class="sxs-lookup"><span data-stu-id="d5c35-116">Parent elements</span></span>

|     | <span data-ttu-id="d5c35-117">説明</span><span class="sxs-lookup"><span data-stu-id="d5c35-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d5c35-118"> **\<動作 >** </span><span class="sxs-lookup"><span data-stu-id="d5c35-118">**\<behavior>**</span></span>](behavior-of-endpointbehaviors.md) | <span data-ttu-id="d5c35-119">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c35-119">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d5c35-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5c35-120">Remarks</span></span>

<span data-ttu-id="d5c35-121">SOAP 処理は、メッセージ バージョン間でメッセージが変換されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="d5c35-121">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="d5c35-122">Windows Communication Foundation (WCF) ルーティングサービスでは、あるプロトコルから別のプロトコルにメッセージを変換できます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-122">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="d5c35-123">受信メッセージのバージョンと送信メッセージのバージョンが異なる場合、新しいメッセージが正しいバージョンで作成されます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-123">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="d5c35-124">受信 WCF メッセージの本文および関連するヘッダーが含まれた新しい WCF メッセージを作成することで、ある <xref:System.ServiceModel.Channels.MessageVersion> から別のメッセージ バージョンへのメッセージの変換が完了します。</span><span class="sxs-lookup"><span data-stu-id="d5c35-124">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="d5c35-125">アドレス指定に固有のヘッダーまたはルーター レベルで認識されるヘッダーは、新しい WCF メッセージの作成に使用されません。これらのヘッダーは、異なるバージョンであるか (アドレス指定ヘッダーの場合)、クライアントとルーターの間の通信の一部として処理されているためです。</span><span class="sxs-lookup"><span data-stu-id="d5c35-125">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="d5c35-126">発信メッセージにヘッダーが配置されるかどうかは、受信チャネル層を介して渡されたと認識されるようにマークされているかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="d5c35-126">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="d5c35-127">認識されないヘッダー (カスタム ヘッダーなど) は削除されずに送信メッセージにコピーされ、ルーティング サービスを介して渡されます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-127">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="d5c35-128">メッセージの本文は、送信メッセージにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-128">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="d5c35-129">そして、メッセージは送信チャネルに送信されます。この時点で、すべてのヘッダー、および使用されている通信プロトコル/トランスポートに固有のエンベロープ データが作成され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-129">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="d5c35-130">このような処理手順は、SOAP 処理動作が指定されているときに行われます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-130">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="d5c35-131">[この\<soapprocessingextension >](soapprocessing.md)動作は、ルーティングサービスの開始時にすべてのクライアント (送信) エンドポイントに適用されるエンドポイントの動作です。</span><span class="sxs-lookup"><span data-stu-id="d5c35-131">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="d5c35-132">既定では、 [ \<ルーティング >](routing-of-servicebehavior.md)動作は、クライアントエンドポイントごとにをに`true`設定`processMessages`して、新しい[ \<soapprocessingextension >](soapprocessing.md)動作を作成してアタッチします。</span><span class="sxs-lookup"><span data-stu-id="d5c35-132">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="d5c35-133">ルーティング サービスが認識しないプロトコルを使用している場合や既定の処理動作をオーバーライドする場合は、ルーティング サービス全体または特定のエンドポイントにおいて SOAP 処理を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-133">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="d5c35-134">すべてのエンドポイントのルーティングサービス全体で SOAP 処理を無効にする`soapProcessing`には、 [ \<ルーティング >](routing-of-servicebehavior.md)動作の`false`属性をに設定します。</span><span class="sxs-lookup"><span data-stu-id="d5c35-134">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="d5c35-135">特定のエンドポイントで SOAP 処理を無効にするには、この動作を使用して `processMessages` 属性を `false` に設定してから、既定の処理コードを実行しないエンドポイントにこの動作をアタッチします。</span><span class="sxs-lookup"><span data-stu-id="d5c35-135">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="d5c35-136">[ \<ルーティング >](routing-of-servicebehavior.md)の動作がルーティングサービスを設定すると、既に存在しているため、エンドポイントの動作の再適用はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="d5c35-136">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>

---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 04e6abc5941ec99769ff2c15d47881b60e81d2e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181572"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="77cb5-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="77cb5-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="77cb5-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="77cb5-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77cb5-104">構文</span><span class="sxs-lookup"><span data-stu-id="77cb5-104">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="77cb5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="77cb5-105">Methods</span></span>  
 <span data-ttu-id="77cb5-106">ConnectionOrientedTransportBindingElement クラスで定義されているメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="77cb5-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="77cb5-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="77cb5-107">Properties</span></span>  
 <span data-ttu-id="77cb5-108">ConnectionOrientedTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="77cb5-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="77cb5-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="77cb5-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="77cb5-110">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="77cb5-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="77cb5-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-112">チャネルの初期化が開始されてからタイムアウトになるまでの時間の長さを示す期間。</span><span class="sxs-lookup"><span data-stu-id="77cb5-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="77cb5-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="77cb5-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="77cb5-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="77cb5-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="77cb5-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-116">クライアントまたサービスからネットワークでシリアル化されたメッセージのチャンクを転送するために使用されるバッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="77cb5-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="77cb5-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="77cb5-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="77cb5-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="77cb5-118">Data type: string</span></span>  
  
 <span data-ttu-id="77cb5-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-120">URI の照合時にサービスに到達するため、ホスト名が使用されたかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="77cb5-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="77cb5-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="77cb5-121">MaxBufferSize</span></span>  
 <span data-ttu-id="77cb5-122">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="77cb5-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="77cb5-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-124">使用するバッファーの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="77cb5-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="77cb5-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="77cb5-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="77cb5-126">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="77cb5-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="77cb5-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-128">メッセージのチャンクまたは完全なメッセージを、送信前にメモリ内のバッファーに残したままにできる最長期間。</span><span class="sxs-lookup"><span data-stu-id="77cb5-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="77cb5-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="77cb5-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="77cb5-130">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="77cb5-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="77cb5-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-132">サービスでの着信接続処理に使用できる保留中の非同期受け入れスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="77cb5-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="77cb5-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="77cb5-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="77cb5-134">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="77cb5-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="77cb5-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-136">保留状態の接続の最大数。</span><span class="sxs-lookup"><span data-stu-id="77cb5-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="77cb5-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="77cb5-137">TransferMode</span></span>  
 <span data-ttu-id="77cb5-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="77cb5-138">Data type: string</span></span>  
  
 <span data-ttu-id="77cb5-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="77cb5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77cb5-140">接続指向トランスポートを使用して、メッセージをバッファーするかまたはストリームするかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="77cb5-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77cb5-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="77cb5-141">Requirements</span></span>  
  
|<span data-ttu-id="77cb5-142">MOF</span><span class="sxs-lookup"><span data-stu-id="77cb5-142">MOF</span></span>|<span data-ttu-id="77cb5-143">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="77cb5-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="77cb5-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="77cb5-144">Namespace</span></span>|<span data-ttu-id="77cb5-145">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="77cb5-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77cb5-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="77cb5-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 04e6abc5941ec99769ff2c15d47881b60e81d2e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973528"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="761f8-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="761f8-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="761f8-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="761f8-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="761f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="761f8-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="761f8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="761f8-105">Methods</span></span>  
 <span data-ttu-id="761f8-106">ConnectionOrientedTransportBindingElement クラスで定義されているメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="761f8-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="761f8-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="761f8-107">Properties</span></span>  
 <span data-ttu-id="761f8-108">ConnectionOrientedTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="761f8-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="761f8-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="761f8-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="761f8-110">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="761f8-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="761f8-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-112">チャネルの初期化が開始されてからタイムアウトになるまでの時間の長さを示す期間。</span><span class="sxs-lookup"><span data-stu-id="761f8-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="761f8-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="761f8-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="761f8-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="761f8-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="761f8-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-116">クライアントまたサービスからネットワークでシリアル化されたメッセージのチャンクを転送するために使用されるバッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="761f8-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="761f8-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="761f8-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="761f8-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="761f8-118">Data type: string</span></span>  
  
 <span data-ttu-id="761f8-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-120">URI の照合時にサービスに到達するため、ホスト名が使用されたかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="761f8-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="761f8-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="761f8-121">MaxBufferSize</span></span>  
 <span data-ttu-id="761f8-122">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="761f8-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="761f8-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-124">使用するバッファーの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="761f8-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="761f8-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="761f8-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="761f8-126">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="761f8-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="761f8-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-128">メッセージのチャンクまたは完全なメッセージを、送信前にメモリ内のバッファーに残したままにできる最長期間。</span><span class="sxs-lookup"><span data-stu-id="761f8-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="761f8-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="761f8-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="761f8-130">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="761f8-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="761f8-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-132">サービスでの着信接続処理に使用できる保留中の非同期受け入れスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="761f8-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="761f8-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="761f8-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="761f8-134">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="761f8-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="761f8-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-136">保留状態の接続の最大数。</span><span class="sxs-lookup"><span data-stu-id="761f8-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="761f8-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="761f8-137">TransferMode</span></span>  
 <span data-ttu-id="761f8-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="761f8-138">Data type: string</span></span>  
  
 <span data-ttu-id="761f8-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="761f8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="761f8-140">接続指向トランスポートを使用して、メッセージをバッファーするかまたはストリームするかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="761f8-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="761f8-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="761f8-141">Requirements</span></span>  
  
|<span data-ttu-id="761f8-142">MOF</span><span class="sxs-lookup"><span data-stu-id="761f8-142">MOF</span></span>|<span data-ttu-id="761f8-143">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="761f8-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="761f8-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="761f8-144">Namespace</span></span>|<span data-ttu-id="761f8-145">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="761f8-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="761f8-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="761f8-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

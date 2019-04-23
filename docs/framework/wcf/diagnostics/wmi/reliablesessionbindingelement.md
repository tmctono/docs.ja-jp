---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: b0a621da43402777cc620f1876bd968a72bb8c12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973110"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="50842-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="50842-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="50842-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="50842-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50842-104">構文</span><span class="sxs-lookup"><span data-stu-id="50842-104">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="50842-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="50842-105">Methods</span></span>  
 <span data-ttu-id="50842-106">ReliableSessionBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="50842-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="50842-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="50842-107">Properties</span></span>  
 <span data-ttu-id="50842-108">ReliableSessionBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="50842-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="50842-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="50842-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="50842-110">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="50842-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="50842-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-112">ファクトリによって作成された信頼できるチャネルで、メッセージの送信元に受信確認を送信するまで送信先が待機する時間</span><span class="sxs-lookup"><span data-stu-id="50842-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="50842-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="50842-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="50842-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="50842-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="50842-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-116">フロー制御を有効にするかどうかを示すブール値</span><span class="sxs-lookup"><span data-stu-id="50842-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="50842-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="50842-117">InactivityTimeout</span></span>  
 <span data-ttu-id="50842-118">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="50842-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="50842-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-120">他の通信相手がチャネルにメッセージを送信せずにいられる最長期間を指定します。他の通信相手がメッセージを送信しない期間がこの値を超えると、チャネルでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="50842-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="50842-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="50842-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="50842-122">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="50842-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="50842-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-124">リスナーで受け入れを待機できるチャネルの最大数。</span><span class="sxs-lookup"><span data-stu-id="50842-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="50842-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="50842-125">MaxRetryCount</span></span>  
 <span data-ttu-id="50842-126">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="50842-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="50842-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-128">基になるチャネルで `Send` を呼び出すことで、信頼できるチャネルが受信確認を受信していないメッセージの再転送を試みる最大回数</span><span class="sxs-lookup"><span data-stu-id="50842-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="50842-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="50842-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="50842-130">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="50842-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="50842-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-132">信頼できるセッションの転送ウィンドウの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="50842-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="50842-133">順序あり</span><span class="sxs-lookup"><span data-stu-id="50842-133">Ordered</span></span>  
 <span data-ttu-id="50842-134">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="50842-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="50842-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-136">メッセージが送信された順序で到着されることを保証するかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="50842-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="50842-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="50842-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="50842-138">データ型 : integer</span><span class="sxs-lookup"><span data-stu-id="50842-138">Data type: integer</span></span>  
  
 <span data-ttu-id="50842-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="50842-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50842-140">信頼できるセッションで使用される WS-ReliableMessaging プロトコルのバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="50842-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50842-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="50842-141">Requirements</span></span>  
  
|<span data-ttu-id="50842-142">MOF</span><span class="sxs-lookup"><span data-stu-id="50842-142">MOF</span></span>|<span data-ttu-id="50842-143">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="50842-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="50842-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="50842-144">Namespace</span></span>|<span data-ttu-id="50842-145">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="50842-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50842-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="50842-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>

---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194067"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="ebe8f-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ebe8f-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="ebe8f-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ebe8f-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebe8f-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ebe8f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ebe8f-105">Methods</span></span>  
 <span data-ttu-id="ebe8f-106">PeerTransportBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="ebe8f-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ebe8f-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebe8f-107">Properties</span></span>  
 <span data-ttu-id="ebe8f-108">PeerTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ebe8f-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="ebe8f-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="ebe8f-109">ListenIPAddress</span></span>  
 <span data-ttu-id="ebe8f-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="ebe8f-110">Data type: string</span></span>  
  
 <span data-ttu-id="ebe8f-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="ebe8f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ebe8f-112">ピア ノードがメッセージをリッスンする IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ebe8f-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="ebe8f-113">ポート</span><span class="sxs-lookup"><span data-stu-id="ebe8f-113">Port</span></span>  
 <span data-ttu-id="ebe8f-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="ebe8f-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ebe8f-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="ebe8f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ebe8f-116">このバインディングがピア チャネル メッセージを処理するネットワーク インターフェイス ポートです。</span><span class="sxs-lookup"><span data-stu-id="ebe8f-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="ebe8f-117">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ebe8f-117">Security</span></span>  
 <span data-ttu-id="ebe8f-118">データの種類:PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ebe8f-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="ebe8f-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="ebe8f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ebe8f-120">ピア トランスポートのセキュリティ設定です。</span><span class="sxs-lookup"><span data-stu-id="ebe8f-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe8f-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="ebe8f-121">Requirements</span></span>  
  
|<span data-ttu-id="ebe8f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ebe8f-122">MOF</span></span>|<span data-ttu-id="ebe8f-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="ebe8f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ebe8f-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="ebe8f-124">Namespace</span></span>|<span data-ttu-id="ebe8f-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="ebe8f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebe8f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebe8f-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

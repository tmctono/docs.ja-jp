---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962958"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="c00a3-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c00a3-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="c00a3-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c00a3-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="c00a3-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c00a3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c00a3-105">Methods</span></span>  
 <span data-ttu-id="c00a3-106">PeerTransportBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="c00a3-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c00a3-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c00a3-107">Properties</span></span>  
 <span data-ttu-id="c00a3-108">PeerTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c00a3-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="c00a3-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="c00a3-109">ListenIPAddress</span></span>  
 <span data-ttu-id="c00a3-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="c00a3-110">Data type: string</span></span>  
  
 <span data-ttu-id="c00a3-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c00a3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c00a3-112">ピア ノードがメッセージをリッスンする IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c00a3-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="c00a3-113">ポート</span><span class="sxs-lookup"><span data-stu-id="c00a3-113">Port</span></span>  
 <span data-ttu-id="c00a3-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="c00a3-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c00a3-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c00a3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c00a3-116">このバインディングがピア チャネル メッセージを処理するネットワーク インターフェイス ポートです。</span><span class="sxs-lookup"><span data-stu-id="c00a3-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="c00a3-117">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c00a3-117">Security</span></span>  
 <span data-ttu-id="c00a3-118">データの種類:PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="c00a3-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="c00a3-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c00a3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c00a3-120">ピア トランスポートのセキュリティ設定です。</span><span class="sxs-lookup"><span data-stu-id="c00a3-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00a3-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="c00a3-121">Requirements</span></span>  
  
|<span data-ttu-id="c00a3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c00a3-122">MOF</span></span>|<span data-ttu-id="c00a3-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="c00a3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c00a3-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="c00a3-124">Namespace</span></span>|<span data-ttu-id="c00a3-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="c00a3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c00a3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c00a3-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

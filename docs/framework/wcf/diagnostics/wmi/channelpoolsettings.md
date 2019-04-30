---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 8900af77d0d385bb68b4b85e1d15be57bb7a8d14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963978"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="97e5e-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="97e5e-102">ChannelPoolSettings</span></span>
<span data-ttu-id="97e5e-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="97e5e-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97e5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="97e5e-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="97e5e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="97e5e-105">Methods</span></span>  
 <span data-ttu-id="97e5e-106">ChannelPoolSettings クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="97e5e-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="97e5e-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97e5e-107">Properties</span></span>  
 <span data-ttu-id="97e5e-108">ChannelPoolSettings クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="97e5e-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="97e5e-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="97e5e-109">IdleTimeout</span></span>  
 <span data-ttu-id="97e5e-110">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="97e5e-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="97e5e-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="97e5e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97e5e-112">接続が切断されるまでの最大アイドル時間。</span><span class="sxs-lookup"><span data-stu-id="97e5e-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="97e5e-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="97e5e-113">LeaseTimeout</span></span>  
 <span data-ttu-id="97e5e-114">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="97e5e-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="97e5e-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="97e5e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97e5e-116">リース操作の完了がタイムアウトするまでの最大時間。</span><span class="sxs-lookup"><span data-stu-id="97e5e-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="97e5e-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="97e5e-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="97e5e-118">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="97e5e-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="97e5e-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="97e5e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97e5e-120">各エンドポイントでの送信チャネルの最大数。</span><span class="sxs-lookup"><span data-stu-id="97e5e-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97e5e-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="97e5e-121">Requirements</span></span>  
  
|<span data-ttu-id="97e5e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="97e5e-122">MOF</span></span>|<span data-ttu-id="97e5e-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="97e5e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="97e5e-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="97e5e-124">Namespace</span></span>|<span data-ttu-id="97e5e-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="97e5e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97e5e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="97e5e-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>

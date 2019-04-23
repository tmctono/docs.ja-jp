---
title: チャネル クラス
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767449"
---
# <a name="channel-class"></a><span data-ttu-id="4215a-102">チャネル クラス</span><span class="sxs-lookup"><span data-stu-id="4215a-102">Channel class</span></span>
<span data-ttu-id="4215a-103">チャネル</span><span class="sxs-lookup"><span data-stu-id="4215a-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4215a-104">構文</span><span class="sxs-lookup"><span data-stu-id="4215a-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4215a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4215a-105">Methods</span></span>  
 <span data-ttu-id="4215a-106">チャネル クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="4215a-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4215a-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4215a-107">Properties</span></span>  
 <span data-ttu-id="4215a-108">チャネル クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="4215a-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="4215a-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="4215a-109">LocalAddress</span></span>  
 <span data-ttu-id="4215a-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="4215a-110">Data type: string</span></span>  
  
 <span data-ttu-id="4215a-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4215a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4215a-112">チャネルのローカル エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4215a-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="4215a-113">ref</span><span class="sxs-lookup"><span data-stu-id="4215a-113">ref</span></span>  
 <span data-ttu-id="4215a-114">データの種類:エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4215a-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="4215a-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4215a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4215a-116">チャネルが接続するエンドポイントへの参照。</span><span class="sxs-lookup"><span data-stu-id="4215a-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="4215a-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="4215a-117">RemoteAddress</span></span>  
 <span data-ttu-id="4215a-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="4215a-118">Data type: string</span></span>  
  
 <span data-ttu-id="4215a-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4215a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4215a-120">チャネルに関連するリモート アドレス。</span><span class="sxs-lookup"><span data-stu-id="4215a-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="4215a-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="4215a-121">SessionId</span></span>  
 <span data-ttu-id="4215a-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="4215a-122">Data type: string</span></span>  
  
 <span data-ttu-id="4215a-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4215a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4215a-124">現在のセッション ID (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="4215a-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="4215a-125">型</span><span class="sxs-lookup"><span data-stu-id="4215a-125">Type</span></span>  
 <span data-ttu-id="4215a-126">データ型: string</span><span class="sxs-lookup"><span data-stu-id="4215a-126">Data type: string</span></span>  
  
 <span data-ttu-id="4215a-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4215a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4215a-128">チャネルの型。</span><span class="sxs-lookup"><span data-stu-id="4215a-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4215a-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="4215a-129">Requirements</span></span>  
  
|<span data-ttu-id="4215a-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4215a-130">MOF</span></span>|<span data-ttu-id="4215a-131">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="4215a-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4215a-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="4215a-132">Namespace</span></span>|<span data-ttu-id="4215a-133">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="4215a-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4215a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4215a-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>

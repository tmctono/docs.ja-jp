---
title: チャネル クラス
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128844"
---
# <a name="channel-class"></a><span data-ttu-id="c711c-102">チャネル クラス</span><span class="sxs-lookup"><span data-stu-id="c711c-102">Channel class</span></span>
<span data-ttu-id="c711c-103">チャネル</span><span class="sxs-lookup"><span data-stu-id="c711c-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c711c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c711c-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c711c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c711c-105">Methods</span></span>  
 <span data-ttu-id="c711c-106">チャネル クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="c711c-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c711c-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c711c-107">Properties</span></span>  
 <span data-ttu-id="c711c-108">チャネル クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c711c-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="c711c-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="c711c-109">LocalAddress</span></span>  
 <span data-ttu-id="c711c-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="c711c-110">Data type: string</span></span>  
  
 <span data-ttu-id="c711c-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c711c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c711c-112">チャネルのローカル エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="c711c-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c711c-113">ref</span><span class="sxs-lookup"><span data-stu-id="c711c-113">ref</span></span>  
 <span data-ttu-id="c711c-114">データの種類:エンドポイント</span><span class="sxs-lookup"><span data-stu-id="c711c-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="c711c-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c711c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c711c-116">チャネルが接続するエンドポイントへの参照。</span><span class="sxs-lookup"><span data-stu-id="c711c-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="c711c-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="c711c-117">RemoteAddress</span></span>  
 <span data-ttu-id="c711c-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="c711c-118">Data type: string</span></span>  
  
 <span data-ttu-id="c711c-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c711c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c711c-120">チャネルに関連するリモート アドレス。</span><span class="sxs-lookup"><span data-stu-id="c711c-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="c711c-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="c711c-121">SessionId</span></span>  
 <span data-ttu-id="c711c-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="c711c-122">Data type: string</span></span>  
  
 <span data-ttu-id="c711c-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c711c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c711c-124">現在のセッション ID (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="c711c-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="c711c-125">型</span><span class="sxs-lookup"><span data-stu-id="c711c-125">Type</span></span>  
 <span data-ttu-id="c711c-126">データ型: string</span><span class="sxs-lookup"><span data-stu-id="c711c-126">Data type: string</span></span>  
  
 <span data-ttu-id="c711c-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c711c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c711c-128">チャネルの型。</span><span class="sxs-lookup"><span data-stu-id="c711c-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c711c-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="c711c-129">Requirements</span></span>  
  
|<span data-ttu-id="c711c-130">MOF</span><span class="sxs-lookup"><span data-stu-id="c711c-130">MOF</span></span>|<span data-ttu-id="c711c-131">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="c711c-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c711c-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="c711c-132">Namespace</span></span>|<span data-ttu-id="c711c-133">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="c711c-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c711c-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="c711c-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>

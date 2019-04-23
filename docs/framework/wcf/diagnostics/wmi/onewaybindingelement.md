---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59769269"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="802ac-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="802ac-102">OneWayBindingElement</span></span>
<span data-ttu-id="802ac-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="802ac-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="802ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="802ac-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="802ac-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="802ac-105">Methods</span></span>  
 <span data-ttu-id="802ac-106">OneWayBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="802ac-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="802ac-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="802ac-107">Properties</span></span>  
 <span data-ttu-id="802ac-108">OneWayBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="802ac-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="802ac-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="802ac-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="802ac-110">データの種類:ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="802ac-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="802ac-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="802ac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="802ac-112">チャネル プールの設定。</span><span class="sxs-lookup"><span data-stu-id="802ac-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="802ac-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="802ac-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="802ac-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="802ac-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="802ac-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="802ac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="802ac-116">許可されるチャネルの最大数。</span><span class="sxs-lookup"><span data-stu-id="802ac-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="802ac-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="802ac-117">PacketRoutable</span></span>  
 <span data-ttu-id="802ac-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="802ac-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="802ac-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="802ac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="802ac-120">パケットがルーティング可能かどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="802ac-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="802ac-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="802ac-121">Requirements</span></span>  
  
|<span data-ttu-id="802ac-122">MOF</span><span class="sxs-lookup"><span data-stu-id="802ac-122">MOF</span></span>|<span data-ttu-id="802ac-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="802ac-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="802ac-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="802ac-124">Namespace</span></span>|<span data-ttu-id="802ac-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="802ac-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="802ac-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="802ac-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>

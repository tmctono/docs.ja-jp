---
title: サービス
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991446"
---
# <a name="service"></a><span data-ttu-id="83c98-102">サービス</span><span class="sxs-lookup"><span data-stu-id="83c98-102">Service</span></span>
<span data-ttu-id="83c98-103">サービス</span><span class="sxs-lookup"><span data-stu-id="83c98-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c98-104">構文</span><span class="sxs-lookup"><span data-stu-id="83c98-104">Syntax</span></span>  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="83c98-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="83c98-105">Methods</span></span>  
 <span data-ttu-id="83c98-106">Service クラスで定義されているメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="83c98-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="83c98-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83c98-107">Properties</span></span>  
 <span data-ttu-id="83c98-108">Service クラスには次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="83c98-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="83c98-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="83c98-109">BaseAddresses</span></span>  
 <span data-ttu-id="83c98-110">データ型 : string array</span><span class="sxs-lookup"><span data-stu-id="83c98-110">Data type: string array</span></span>  
  
 <span data-ttu-id="83c98-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-112">サービスによって使用されるベース アドレスです。</span><span class="sxs-lookup"><span data-stu-id="83c98-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="83c98-113">ビヘイビアー</span><span class="sxs-lookup"><span data-stu-id="83c98-113">Behaviors</span></span>  
 <span data-ttu-id="83c98-114">データの種類:動作の配列</span><span class="sxs-lookup"><span data-stu-id="83c98-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="83c98-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-116">このサービスに関連付けられている動作です。</span><span class="sxs-lookup"><span data-stu-id="83c98-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="83c98-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="83c98-117">ConfigurationName</span></span>  
 <span data-ttu-id="83c98-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="83c98-118">Data type: string</span></span>  
  
 <span data-ttu-id="83c98-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="83c98-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="83c98-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="83c98-121">CounterInstanceName</span></span>  
 <span data-ttu-id="83c98-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="83c98-122">Data type: string</span></span>  
  
 <span data-ttu-id="83c98-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-124">サービスのパフォーマンス カウンターのインスタンスのインスタンス名です。</span><span class="sxs-lookup"><span data-stu-id="83c98-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="83c98-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="83c98-125">DistinguishedName</span></span>  
 <span data-ttu-id="83c98-126">データ型: string</span><span class="sxs-lookup"><span data-stu-id="83c98-126">Data type: string</span></span>  
  
 <span data-ttu-id="83c98-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-128">アドレスでのサービス名です。</span><span class="sxs-lookup"><span data-stu-id="83c98-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="83c98-129">拡張機能</span><span class="sxs-lookup"><span data-stu-id="83c98-129">Extensions</span></span>  
 <span data-ttu-id="83c98-130">データ型 : string array</span><span class="sxs-lookup"><span data-stu-id="83c98-130">Data type: string array</span></span>  
  
 <span data-ttu-id="83c98-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-132">サービス インスタンスの拡張に対するインスタンス コンテキストです。</span><span class="sxs-lookup"><span data-stu-id="83c98-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="83c98-133">メタデータ</span><span class="sxs-lookup"><span data-stu-id="83c98-133">Metadata</span></span>  
 <span data-ttu-id="83c98-134">データ型 : string array</span><span class="sxs-lookup"><span data-stu-id="83c98-134">Data type: string array</span></span>  
  
 <span data-ttu-id="83c98-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-136">サービス メタデータの設定です。</span><span class="sxs-lookup"><span data-stu-id="83c98-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="83c98-137">名前</span><span class="sxs-lookup"><span data-stu-id="83c98-137">Name</span></span>  
 <span data-ttu-id="83c98-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="83c98-138">Data type: string</span></span>  
  
 <span data-ttu-id="83c98-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-140">このサービスの一意の名前。</span><span class="sxs-lookup"><span data-stu-id="83c98-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="83c98-141">名前空間</span><span class="sxs-lookup"><span data-stu-id="83c98-141">Namespace</span></span>  
 <span data-ttu-id="83c98-142">データ型: string</span><span class="sxs-lookup"><span data-stu-id="83c98-142">Data type: string</span></span>  
  
 <span data-ttu-id="83c98-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-144">サービスの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="83c98-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="83c98-145">Opened</span><span class="sxs-lookup"><span data-stu-id="83c98-145">Opened</span></span>  
 <span data-ttu-id="83c98-146">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="83c98-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="83c98-147">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-148">サービスが開かれた時刻です。</span><span class="sxs-lookup"><span data-stu-id="83c98-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="83c98-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="83c98-149">OutgoingChannels</span></span>  
 <span data-ttu-id="83c98-150">データの種類:チャネルの配列</span><span class="sxs-lookup"><span data-stu-id="83c98-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="83c98-151">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-152">サービス インスタンスから送信しているチャネルです。</span><span class="sxs-lookup"><span data-stu-id="83c98-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="83c98-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="83c98-153">ProcessId</span></span>  
 <span data-ttu-id="83c98-154">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="83c98-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="83c98-155">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="83c98-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83c98-156">サービスをホストするプロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="83c98-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c98-157">必要条件</span><span class="sxs-lookup"><span data-stu-id="83c98-157">Requirements</span></span>  
  
|<span data-ttu-id="83c98-158">MOF</span><span class="sxs-lookup"><span data-stu-id="83c98-158">MOF</span></span>|<span data-ttu-id="83c98-159">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="83c98-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="83c98-160">名前空間</span><span class="sxs-lookup"><span data-stu-id="83c98-160">Namespace</span></span>|<span data-ttu-id="83c98-161">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="83c98-161">Defined in root\ServiceModel</span></span>|

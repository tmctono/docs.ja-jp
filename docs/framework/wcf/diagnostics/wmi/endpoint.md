---
title: エンドポイント
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795898"
---
# <a name="endpoint"></a><span data-ttu-id="b938f-102">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="b938f-102">Endpoint</span></span>
<span data-ttu-id="b938f-103">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="b938f-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b938f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b938f-104">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b938f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b938f-105">Methods</span></span>  
 <span data-ttu-id="b938f-106">Endpoint クラスは次のメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="b938f-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="b938f-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="b938f-107">Method</span></span>|<span data-ttu-id="b938f-108">説明</span><span class="sxs-lookup"><span data-stu-id="b938f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b938f-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="b938f-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="b938f-110">操作パフォーマンス カウンターのインスタンスの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="b938f-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="b938f-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b938f-111">Properties</span></span>  
 <span data-ttu-id="b938f-112">Endpoint クラスには次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b938f-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="b938f-113">Address</span><span class="sxs-lookup"><span data-stu-id="b938f-113">Address</span></span>  
 <span data-ttu-id="b938f-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b938f-114">Data type: string</span></span>  
  
 <span data-ttu-id="b938f-115">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-116">エンドポイントのアドレスを格納している URI。</span><span class="sxs-lookup"><span data-stu-id="b938f-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="b938f-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="b938f-117">AddressHeaders</span></span>  
 <span data-ttu-id="b938f-118">データ型 : string array</span><span class="sxs-lookup"><span data-stu-id="b938f-118">Data type: string array</span></span>  
  
 <span data-ttu-id="b938f-119">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-120">このエンドポイントに接続しているアドレス ヘッダーのコレクション</span><span class="sxs-lookup"><span data-stu-id="b938f-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="b938f-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="b938f-121">AddressIdentity</span></span>  
 <span data-ttu-id="b938f-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b938f-122">Data type: string</span></span>  
  
 <span data-ttu-id="b938f-123">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-124">エンドポイントの ID</span><span class="sxs-lookup"><span data-stu-id="b938f-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="b938f-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="b938f-125">AppDomainId</span></span>  
 <span data-ttu-id="b938f-126">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="b938f-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="b938f-127">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-128">エンドポイントをホストする appdomain の appdomain ID</span><span class="sxs-lookup"><span data-stu-id="b938f-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="b938f-129">ビヘイビアー</span><span class="sxs-lookup"><span data-stu-id="b938f-129">Behaviors</span></span>  
 <span data-ttu-id="b938f-130">データの種類:動作の配列</span><span class="sxs-lookup"><span data-stu-id="b938f-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="b938f-131">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-132">このエンドポイントが実装する動作のコレクション</span><span class="sxs-lookup"><span data-stu-id="b938f-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="b938f-133">バインディング</span><span class="sxs-lookup"><span data-stu-id="b938f-133">Binding</span></span>  
 <span data-ttu-id="b938f-134">データの種類:バインディング</span><span class="sxs-lookup"><span data-stu-id="b938f-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="b938f-135">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-136">このエンドポイントが使用するバインディング</span><span class="sxs-lookup"><span data-stu-id="b938f-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="b938f-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="b938f-137">ContractName</span></span>  
 <span data-ttu-id="b938f-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b938f-138">Data type: string</span></span>  
  
 <span data-ttu-id="b938f-139">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-140">このエンドポイントが公開するコントラクトを指定する文字列</span><span class="sxs-lookup"><span data-stu-id="b938f-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="b938f-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="b938f-141">CounterInstanceName</span></span>  
 <span data-ttu-id="b938f-142">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b938f-142">Data type: string</span></span>  
  
 <span data-ttu-id="b938f-143">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-144">エンドポイントのパフォーマンス カウンターのインスタンス名</span><span class="sxs-lookup"><span data-stu-id="b938f-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="b938f-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="b938f-145">ListenUri</span></span>  
 <span data-ttu-id="b938f-146">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b938f-146">Data type: string</span></span>  
  
 <span data-ttu-id="b938f-147">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-148">エンドポイントがリッスンする URI</span><span class="sxs-lookup"><span data-stu-id="b938f-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b938f-149">Name</span><span class="sxs-lookup"><span data-stu-id="b938f-149">Name</span></span>  
 <span data-ttu-id="b938f-150">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b938f-150">Data type: string</span></span>  
  
 <span data-ttu-id="b938f-151">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-152">このエンドポイントの一意の名前</span><span class="sxs-lookup"><span data-stu-id="b938f-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b938f-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b938f-153">ProcessId</span></span>  
 <span data-ttu-id="b938f-154">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="b938f-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="b938f-155">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-156">エンドポイントをホストするプロセスのプロセス ID</span><span class="sxs-lookup"><span data-stu-id="b938f-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="b938f-157">ref</span><span class="sxs-lookup"><span data-stu-id="b938f-157">ref</span></span>  
 <span data-ttu-id="b938f-158">データの種類:コントラクト</span><span class="sxs-lookup"><span data-stu-id="b938f-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="b938f-159">アクセスの種類:読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b938f-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b938f-160">このエンドポイントが公開しているコントラクト。</span><span class="sxs-lookup"><span data-stu-id="b938f-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b938f-161">必要条件</span><span class="sxs-lookup"><span data-stu-id="b938f-161">Requirements</span></span>  
  
|<span data-ttu-id="b938f-162">MOF</span><span class="sxs-lookup"><span data-stu-id="b938f-162">MOF</span></span>|<span data-ttu-id="b938f-163">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="b938f-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b938f-164">名前空間</span><span class="sxs-lookup"><span data-stu-id="b938f-164">Namespace</span></span>|<span data-ttu-id="b938f-165">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="b938f-165">Defined in root\ServiceModel</span></span>|

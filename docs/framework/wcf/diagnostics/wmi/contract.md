---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773000"
---
# <a name="contract"></a><span data-ttu-id="58a70-102">コントラクト</span><span class="sxs-lookup"><span data-stu-id="58a70-102">Contract</span></span>
<span data-ttu-id="58a70-103">コントラクト</span><span class="sxs-lookup"><span data-stu-id="58a70-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58a70-104">構文</span><span class="sxs-lookup"><span data-stu-id="58a70-104">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="58a70-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="58a70-105">Methods</span></span>  
 <span data-ttu-id="58a70-106">Contract クラスで定義されているメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="58a70-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="58a70-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="58a70-107">Properties</span></span>  
 <span data-ttu-id="58a70-108">Contract クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="58a70-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="58a70-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="58a70-109">AppDomainId</span></span>  
 <span data-ttu-id="58a70-110">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="58a70-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="58a70-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-112">コントラクトをホストする appdomain の appdomain ID。</span><span class="sxs-lookup"><span data-stu-id="58a70-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="58a70-113">ビヘイビアー</span><span class="sxs-lookup"><span data-stu-id="58a70-113">Behaviors</span></span>  
 <span data-ttu-id="58a70-114">データの種類:動作の配列</span><span class="sxs-lookup"><span data-stu-id="58a70-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="58a70-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-116">このコントラクトに関連付けられている動作。</span><span class="sxs-lookup"><span data-stu-id="58a70-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="58a70-117">名前</span><span class="sxs-lookup"><span data-stu-id="58a70-117">Name</span></span>  
 <span data-ttu-id="58a70-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="58a70-118">Data type: string</span></span>  
  
 <span data-ttu-id="58a70-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-120">WSDL でのコントラクトの名前。</span><span class="sxs-lookup"><span data-stu-id="58a70-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="58a70-121">名前空間</span><span class="sxs-lookup"><span data-stu-id="58a70-121">Namespace</span></span>  
 <span data-ttu-id="58a70-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="58a70-122">Data type: string</span></span>  
  
 <span data-ttu-id="58a70-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-124">WSDL での `portType` 要素の名前空間。</span><span class="sxs-lookup"><span data-stu-id="58a70-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="58a70-125">操作</span><span class="sxs-lookup"><span data-stu-id="58a70-125">Operations</span></span>  
 <span data-ttu-id="58a70-126">データの種類:配列の操作</span><span class="sxs-lookup"><span data-stu-id="58a70-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="58a70-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-128">このコントラクトの操作。</span><span class="sxs-lookup"><span data-stu-id="58a70-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="58a70-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="58a70-129">ProcessId</span></span>  
 <span data-ttu-id="58a70-130">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="58a70-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="58a70-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-132">コントラクトをホストするプロセスのプロセス ID。</span><span class="sxs-lookup"><span data-stu-id="58a70-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="58a70-133">ref</span><span class="sxs-lookup"><span data-stu-id="58a70-133">ref</span></span>  
 <span data-ttu-id="58a70-134">データの種類:コントラクト</span><span class="sxs-lookup"><span data-stu-id="58a70-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="58a70-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-136">コントラクトが双方向コントラクトのときのコールバックの型。</span><span class="sxs-lookup"><span data-stu-id="58a70-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="58a70-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="58a70-137">SessionMode</span></span>  
 <span data-ttu-id="58a70-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="58a70-138">Data type: string</span></span>  
  
 <span data-ttu-id="58a70-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-140">コントラクトでチャネル セッションを使用するために、このコントラクトに関連付けられたバインディングが必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="58a70-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="58a70-141">型</span><span class="sxs-lookup"><span data-stu-id="58a70-141">Type</span></span>  
 <span data-ttu-id="58a70-142">データ型: string</span><span class="sxs-lookup"><span data-stu-id="58a70-142">Data type: string</span></span>  
  
 <span data-ttu-id="58a70-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="58a70-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58a70-144">コントラクトの型。</span><span class="sxs-lookup"><span data-stu-id="58a70-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a70-145">必要条件</span><span class="sxs-lookup"><span data-stu-id="58a70-145">Requirements</span></span>  
  
|<span data-ttu-id="58a70-146">MOF</span><span class="sxs-lookup"><span data-stu-id="58a70-146">MOF</span></span>|<span data-ttu-id="58a70-147">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="58a70-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="58a70-148">名前空間</span><span class="sxs-lookup"><span data-stu-id="58a70-148">Namespace</span></span>|<span data-ttu-id="58a70-149">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="58a70-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58a70-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="58a70-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>

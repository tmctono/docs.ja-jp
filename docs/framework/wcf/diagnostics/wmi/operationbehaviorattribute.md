---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963047"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="e2dd7-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="e2dd7-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="e2dd7-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="e2dd7-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2dd7-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2dd7-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e2dd7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e2dd7-105">Methods</span></span>  
 <span data-ttu-id="e2dd7-106">OperationBehaviorAttribute クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e2dd7-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e2dd7-107">Properties</span></span>  
 <span data-ttu-id="e2dd7-108">OperationBehaviorAttribute クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="e2dd7-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="e2dd7-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="e2dd7-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="e2dd7-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2dd7-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="e2dd7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2dd7-112">パラメーターの自動破棄機能の状態です。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="e2dd7-113">偽装</span><span class="sxs-lookup"><span data-stu-id="e2dd7-113">Impersonation</span></span>  
 <span data-ttu-id="e2dd7-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="e2dd7-114">Data type: string</span></span>  
  
 <span data-ttu-id="e2dd7-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="e2dd7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2dd7-116">操作がサポートする、呼び出し元の偽装レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="e2dd7-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="e2dd7-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="e2dd7-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="e2dd7-118">Data type: string</span></span>  
  
 <span data-ttu-id="e2dd7-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="e2dd7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2dd7-120">操作の呼び出し過程のどの時点でオブジェクトをリサイクルするかを示します。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="e2dd7-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="e2dd7-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="e2dd7-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="e2dd7-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2dd7-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="e2dd7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2dd7-124">未処理の例外が発生しなかった場合に、現在のトランザクションを自動的にコミットするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="e2dd7-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="e2dd7-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="e2dd7-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="e2dd7-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2dd7-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="e2dd7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2dd7-128">操作がトランザクションを必要とするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2dd7-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="e2dd7-129">Requirements</span></span>  
  
|<span data-ttu-id="e2dd7-130">MOF</span><span class="sxs-lookup"><span data-stu-id="e2dd7-130">MOF</span></span>|<span data-ttu-id="e2dd7-131">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="e2dd7-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e2dd7-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="e2dd7-132">Namespace</span></span>|<span data-ttu-id="e2dd7-133">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="e2dd7-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2dd7-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2dd7-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>

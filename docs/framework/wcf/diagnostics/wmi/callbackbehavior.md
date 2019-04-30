---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963957"
---
# <a name="callbackbehavior"></a><span data-ttu-id="00aba-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="00aba-102">CallbackBehavior</span></span>
<span data-ttu-id="00aba-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="00aba-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00aba-104">構文</span><span class="sxs-lookup"><span data-stu-id="00aba-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="00aba-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="00aba-105">Methods</span></span>  
 <span data-ttu-id="00aba-106">CallbackBehavior クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="00aba-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="00aba-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="00aba-107">Properties</span></span>  
 <span data-ttu-id="00aba-108">CallbackBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="00aba-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="00aba-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="00aba-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="00aba-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="00aba-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="00aba-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-112">true の場合、サービスが双方向セッションを閉じると、セッションが自動的に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="00aba-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="00aba-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="00aba-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="00aba-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="00aba-114">Data type: string</span></span>  
<span data-ttu-id="00aba-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-116">サービスが単一のスレッド、複数のスレッド、再入可能呼び出しのいずれをサポートするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="00aba-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="00aba-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="00aba-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="00aba-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="00aba-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="00aba-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-120">不明なシリアル化データをネットワークで送信するかどうかを指定する値です。</span><span class="sxs-lookup"><span data-stu-id="00aba-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="00aba-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="00aba-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="00aba-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="00aba-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="00aba-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-124">有効にした場合は、コールバックの例外に関する詳細情報が、サービスに戻されるエラーに添付されます。</span><span class="sxs-lookup"><span data-stu-id="00aba-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="00aba-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="00aba-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="00aba-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="00aba-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="00aba-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-128">1 つのシリアル化されたオブジェクトで許可される項目の最大数。</span><span class="sxs-lookup"><span data-stu-id="00aba-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="00aba-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="00aba-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="00aba-130">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="00aba-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="00aba-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-132">現在の同期コンテキストを使用して実行のスレッドを選択するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="00aba-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="00aba-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="00aba-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="00aba-134">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="00aba-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="00aba-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="00aba-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00aba-136">システムまたはアプリケーションで SOAP MustUnderstand ヘッダー処理を強制的に行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="00aba-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00aba-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="00aba-137">Requirements</span></span>  
  
|<span data-ttu-id="00aba-138">MOF</span><span class="sxs-lookup"><span data-stu-id="00aba-138">MOF</span></span>|<span data-ttu-id="00aba-139">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="00aba-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="00aba-140">名前空間</span><span class="sxs-lookup"><span data-stu-id="00aba-140">Namespace</span></span>|<span data-ttu-id="00aba-141">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="00aba-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00aba-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="00aba-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>

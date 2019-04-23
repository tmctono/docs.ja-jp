---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772831"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="5d1d7-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="5d1d7-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="5d1d7-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="5d1d7-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d1d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d1d7-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5d1d7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5d1d7-105">Methods</span></span>  
 <span data-ttu-id="5d1d7-106">ServiceBehaviorAttribute クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5d1d7-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5d1d7-107">Properties</span></span>  
 <span data-ttu-id="5d1d7-108">ServiceBehaviorAttribute クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="5d1d7-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="5d1d7-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="5d1d7-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-112">クライアントが出力セッションを閉じるときにセッションを自動的に閉じるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="5d1d7-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="5d1d7-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="5d1d7-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="5d1d7-114">Data type: string</span></span>  
<span data-ttu-id="5d1d7-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-116">サービスで、1 つのスレッド、複数のスレッド、または再入呼び出しをサポートするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="5d1d7-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="5d1d7-117">ConfigurationName</span></span>  
 <span data-ttu-id="5d1d7-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="5d1d7-118">Data type: string</span></span>  
  
 <span data-ttu-id="5d1d7-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-120">サービス構成の名前。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="5d1d7-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="5d1d7-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="5d1d7-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-124">不明なシリアル化データをネットワークで送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="5d1d7-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="5d1d7-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="5d1d7-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-128">デバッグの目的でクライアントに返される SOAP エラーの詳細に、マネージド例外情報を含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="5d1d7-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="5d1d7-129">InstanceContextMode</span></span>  
 <span data-ttu-id="5d1d7-130">データ型: string</span><span class="sxs-lookup"><span data-stu-id="5d1d7-130">Data type: string</span></span>  
  
 <span data-ttu-id="5d1d7-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-132">新しいサービス オブジェクトを作成するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="5d1d7-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="5d1d7-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="5d1d7-134">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="5d1d7-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="5d1d7-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-136">1 つのシリアル化されたオブジェクトで許可される項目の最大数。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="5d1d7-137">名前</span><span class="sxs-lookup"><span data-stu-id="5d1d7-137">Name</span></span>  
 <span data-ttu-id="5d1d7-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="5d1d7-138">Data type: string</span></span>  
  
 <span data-ttu-id="5d1d7-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-140">WSDL でのサービスの名前属性。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="5d1d7-141">名前空間</span><span class="sxs-lookup"><span data-stu-id="5d1d7-141">Namespace</span></span>  
 <span data-ttu-id="5d1d7-142">データ型: string</span><span class="sxs-lookup"><span data-stu-id="5d1d7-142">Data type: string</span></span>  
  
 <span data-ttu-id="5d1d7-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-144">WSDL でのサービスのターゲット名前空間。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="5d1d7-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="5d1d7-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="5d1d7-146">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-147">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-148">現在のトランザクションの完了時に、サービス オブジェクトをリサイクルするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="5d1d7-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="5d1d7-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="5d1d7-150">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-151">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-152">現在のセッションの終了時に、保留中のトランザクションを完了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="5d1d7-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="5d1d7-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="5d1d7-154">データ型: string</span><span class="sxs-lookup"><span data-stu-id="5d1d7-154">Data type: string</span></span>  
  
 <span data-ttu-id="5d1d7-155">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-156">トランザクションの分離レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="5d1d7-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="5d1d7-157">TransactionTimeout</span></span>  
 <span data-ttu-id="5d1d7-158">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="5d1d7-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="5d1d7-159">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-160">トランザクションを完了しなければならない期間。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="5d1d7-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="5d1d7-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="5d1d7-162">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-163">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-164">現在の同期コンテキストを使用してスレッドの実行を選択するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="5d1d7-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="5d1d7-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="5d1d7-166">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="5d1d7-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d1d7-167">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="5d1d7-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d1d7-168">システムまたはアプリケーションで SOAP MustUnderstand ヘッダー処理を強制的に行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d1d7-169">必要条件</span><span class="sxs-lookup"><span data-stu-id="5d1d7-169">Requirements</span></span>  
  
|<span data-ttu-id="5d1d7-170">MOF</span><span class="sxs-lookup"><span data-stu-id="5d1d7-170">MOF</span></span>|<span data-ttu-id="5d1d7-171">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="5d1d7-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5d1d7-172">名前空間</span><span class="sxs-lookup"><span data-stu-id="5d1d7-172">Namespace</span></span>|<span data-ttu-id="5d1d7-173">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="5d1d7-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d1d7-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d1d7-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>

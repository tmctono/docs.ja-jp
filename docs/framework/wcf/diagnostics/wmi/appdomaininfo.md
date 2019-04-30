---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964256"
---
# <a name="appdomaininfo"></a><span data-ttu-id="b4757-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="b4757-102">AppDomainInfo</span></span>
<span data-ttu-id="b4757-103">アプリケーション ドメイン情報</span><span class="sxs-lookup"><span data-stu-id="b4757-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4757-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4757-104">Syntax</span></span>  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b4757-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4757-105">Methods</span></span>  
 <span data-ttu-id="b4757-106">AppDomainInfo クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="b4757-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b4757-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b4757-107">Properties</span></span>  
 <span data-ttu-id="b4757-108">AppDomainInfo クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b4757-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="b4757-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="b4757-109">AppDomainId</span></span>  
 <span data-ttu-id="b4757-110">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="b4757-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="b4757-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-112">AppDomain の ID です。</span><span class="sxs-lookup"><span data-stu-id="b4757-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="b4757-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="b4757-113">IsDefault</span></span>  
 <span data-ttu-id="b4757-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b4757-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4757-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-116">AppDomain が既定の AppDomain かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b4757-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="b4757-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="b4757-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="b4757-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b4757-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4757-119">アクセスの種類:[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="b4757-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4757-120">非整形式メッセージをログに記録するかどうかを指定する値です。</span><span class="sxs-lookup"><span data-stu-id="b4757-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="b4757-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="b4757-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="b4757-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b4757-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4757-123">アクセスの種類:[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="b4757-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4757-124">メッセージをサービス レベルでトレースするかどうかを指定する値です (暗号化およびトランスポート関連の変換前)。</span><span class="sxs-lookup"><span data-stu-id="b4757-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="b4757-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="b4757-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="b4757-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b4757-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4757-127">アクセスの種類:[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="b4757-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4757-128">メッセージをトランスポート レベルでトレースするかどうかを指定する値です。</span><span class="sxs-lookup"><span data-stu-id="b4757-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="b4757-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="b4757-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="b4757-130">データの種類:TraceListener 配列</span><span class="sxs-lookup"><span data-stu-id="b4757-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="b4757-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-132">System.Wmi.MessageLogging トレース ソースをリッスンするコレクション トレース リスナーです。</span><span class="sxs-lookup"><span data-stu-id="b4757-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b4757-133">名前</span><span class="sxs-lookup"><span data-stu-id="b4757-133">Name</span></span>  
 <span data-ttu-id="b4757-134">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b4757-134">Data type: string</span></span>  
  
 <span data-ttu-id="b4757-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-136">AppDomain の名前です。</span><span class="sxs-lookup"><span data-stu-id="b4757-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="b4757-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="b4757-137">PerformanceCounters</span></span>  
 <span data-ttu-id="b4757-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b4757-138">Data type: string</span></span>  
  
 <span data-ttu-id="b4757-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-140">AppDomain におけるアクティブなパフォーマンス カウンターのスコープです。</span><span class="sxs-lookup"><span data-stu-id="b4757-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b4757-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b4757-141">ProcessId</span></span>  
 <span data-ttu-id="b4757-142">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="b4757-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="b4757-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-144">プロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="b4757-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="b4757-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="b4757-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="b4757-146">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b4757-146">Data type: string</span></span>  
  
 <span data-ttu-id="b4757-147">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-148">サービスの構成へのパスです。</span><span class="sxs-lookup"><span data-stu-id="b4757-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="b4757-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="b4757-149">TraceLevel</span></span>  
 <span data-ttu-id="b4757-150">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b4757-150">Data type: string</span></span>  
  
 <span data-ttu-id="b4757-151">アクセスの種類:[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="b4757-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="b4757-152">System.Wmi トレース ソースのトレース レベル。</span><span class="sxs-lookup"><span data-stu-id="b4757-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="b4757-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="b4757-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="b4757-154">データの種類:TraceListener 配列</span><span class="sxs-lookup"><span data-stu-id="b4757-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="b4757-155">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b4757-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4757-156">System.ServiceModel トレース ソースのリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="b4757-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4757-157">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4757-157">Requirements</span></span>  
  
|<span data-ttu-id="b4757-158">MOF</span><span class="sxs-lookup"><span data-stu-id="b4757-158">MOF</span></span>|<span data-ttu-id="b4757-159">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="b4757-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b4757-160">名前空間</span><span class="sxs-lookup"><span data-stu-id="b4757-160">Namespace</span></span>|<span data-ttu-id="b4757-161">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="b4757-161">Defined in root\ServiceModel</span></span>|

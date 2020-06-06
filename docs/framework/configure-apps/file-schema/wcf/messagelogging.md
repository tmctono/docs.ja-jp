---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: 9291c38af28c18d20e23e34e8316b4a9fe523123
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855121"
---
# \<messageLogging>
<span data-ttu-id="4c14c-101">この要素は Windows Communication Foundation (WCF) のメッセージ ログ機能の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4c14c-101">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a><span data-ttu-id="4c14c-102">構文</span><span class="sxs-lookup"><span data-stu-id="4c14c-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c14c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4c14c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4c14c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c14c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c14c-105">属性</span><span class="sxs-lookup"><span data-stu-id="4c14c-105">Attributes</span></span>  
  
|<span data-ttu-id="4c14c-106">属性</span><span class="sxs-lookup"><span data-stu-id="4c14c-106">Attribute</span></span>|<span data-ttu-id="4c14c-107">説明</span><span class="sxs-lookup"><span data-stu-id="4c14c-107">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="4c14c-108">メッセージ全体 (メッセージ ヘッダーと本文) を記録するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="4c14c-108">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="4c14c-109">既定は `false` で、メッセージ ヘッダーだけが記録されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-109">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="4c14c-110">この設定は、すべてのメッセージ ログ レベル (サービス、トランスポート、および不正) に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-110">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="4c14c-111">無効なメッセージを記録するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="4c14c-111">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="4c14c-112">無効なメッセージは、`maxMessagesToLog` にカウントされません。</span><span class="sxs-lookup"><span data-stu-id="4c14c-112">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="4c14c-113">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="4c14c-113">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="4c14c-114">(暗号化およびトランスポートに関連する変換の前に) メッセージをサービス レベルでトレースするかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="4c14c-114">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="4c14c-115">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="4c14c-115">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="4c14c-116">メッセージをトランスポート レベルでトレースするかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="4c14c-116">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="4c14c-117">構成ファイルに指定されたフィルターが適用され、フィルターに一致するメッセージだけがトレースされます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-117">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="4c14c-118">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="4c14c-118">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="4c14c-119">記録するメッセージの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="4c14c-119">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="4c14c-120">既定値は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="4c14c-120">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="4c14c-121">記録するメッセージの最大サイズ (バイト単位) を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="4c14c-121">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="4c14c-122">サイズが制限より大きなメッセージは、記録されません。</span><span class="sxs-lookup"><span data-stu-id="4c14c-122">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="4c14c-123">この設定は、すべてのトレース レベルに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-123">This setting affects all trace levels.</span></span> <span data-ttu-id="4c14c-124">既定値は 262144 (0x4000) です。</span><span class="sxs-lookup"><span data-stu-id="4c14c-124">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c14c-125">子要素</span><span class="sxs-lookup"><span data-stu-id="4c14c-125">Child Elements</span></span>  
  
|<span data-ttu-id="4c14c-126">要素</span><span class="sxs-lookup"><span data-stu-id="4c14c-126">Element</span></span>|<span data-ttu-id="4c14c-127">Description</span><span class="sxs-lookup"><span data-stu-id="4c14c-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c14c-128">filters</span><span class="sxs-lookup"><span data-stu-id="4c14c-128">filters</span></span>|<span data-ttu-id="4c14c-129">`filters` 要素には、XPath フィルターのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-129">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="4c14c-130">トランスポート メッセージ ログが有効な場合 (`logMessagesAtTransportLevel` が `true`)、フィルターに一致するメッセージだけが記録されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-130">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="4c14c-131">フィルターは、トランスポート層でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-131">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="4c14c-132">サービス レベルおよび形式が正しくないメッセージ ログ記録は、フィルターの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="4c14c-132">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="4c14c-133">この要素の唯一の属性である `filter` は、XpathFilter です。</span><span class="sxs-lookup"><span data-stu-id="4c14c-133">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c14c-134">親要素</span><span class="sxs-lookup"><span data-stu-id="4c14c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="4c14c-135">要素</span><span class="sxs-lookup"><span data-stu-id="4c14c-135">Element</span></span>|<span data-ttu-id="4c14c-136">Description</span><span class="sxs-lookup"><span data-stu-id="4c14c-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c14c-137">診断</span><span class="sxs-lookup"><span data-stu-id="4c14c-137">diagnostics</span></span>|<span data-ttu-id="4c14c-138">管理者が行うランタイムの検査と管理の WCF 設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4c14c-138">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c14c-139">解説</span><span class="sxs-lookup"><span data-stu-id="4c14c-139">Remarks</span></span>  
 <span data-ttu-id="4c14c-140">メッセージは、サービス、トランスポート、および不正の 3 種類のレベルで記録されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-140">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="4c14c-141">各レベルは、個別にアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-141">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="4c14c-142">XPath フィルターは、トランスポート レベルとサービス レベルで特定のメッセージを記録するために追加できます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-142">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="4c14c-143">フィルターが定義されていない場合、すべてのメッセージが記録されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-143">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="4c14c-144">フィルターは、メッセージのヘッダーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-144">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="4c14c-145">本文は無視されます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-145">The body is ignored.</span></span> <span data-ttu-id="4c14c-146">WCF は、パフォーマンスを強化するためにメッセージ本文を無視します。</span><span class="sxs-lookup"><span data-stu-id="4c14c-146">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="4c14c-147">本文の内容に基づいてフィルターを適用する場合は、そのためのフィルターを備えたカスタム リスナーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-147">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="4c14c-148">メッセージ トレースをアクティブ化するために、トレース リスナーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c14c-148">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="4c14c-149">リスナー自体には、<xref:System.Diagnostics> トレース アーキテクチャで動作するリスナーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c14c-149">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="4c14c-150">次の例は、そのようなリスナーの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4c14c-150">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a><span data-ttu-id="4c14c-151">例</span><span class="sxs-lookup"><span data-stu-id="4c14c-151">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="4c14c-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c14c-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="4c14c-153">メッセージ ログの構成</span><span class="sxs-lookup"><span data-stu-id="4c14c-153">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)

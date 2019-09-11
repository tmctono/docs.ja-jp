---
title: <add> の <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850566"
---
# <a name="add-of-filters"></a><span data-ttu-id="674ca-102">\<フィルターの > \<を追加する ></span><span class="sxs-lookup"><span data-stu-id="674ca-102">\<add> of \<filters></span></span>
<span data-ttu-id="674ca-103">ログに記録するメッセージの種類を指定する XPath フィルター。</span><span class="sxs-lookup"><span data-stu-id="674ca-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
<span data-ttu-id="674ca-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="674ca-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="674ca-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="674ca-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="674ca-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<診断 >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="674ca-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="674ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<messageLogging >** ](messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="674ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)</span></span>\
<span data-ttu-id="674ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<フィルター >** ](filters.md)</span><span class="sxs-lookup"><span data-stu-id="674ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)</span></span>\
<span data-ttu-id="674ca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="674ca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="674ca-110">構文</span><span class="sxs-lookup"><span data-stu-id="674ca-110">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="674ca-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="674ca-111">Attributes and Elements</span></span>  
 <span data-ttu-id="674ca-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="674ca-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="674ca-113">属性</span><span class="sxs-lookup"><span data-stu-id="674ca-113">Attributes</span></span>  
  
|<span data-ttu-id="674ca-114">属性</span><span class="sxs-lookup"><span data-stu-id="674ca-114">Attribute</span></span>|<span data-ttu-id="674ca-115">説明</span><span class="sxs-lookup"><span data-stu-id="674ca-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="674ca-116">filter</span><span class="sxs-lookup"><span data-stu-id="674ca-116">filter</span></span>|<span data-ttu-id="674ca-117">XPath 1.0 の式によって定義される、XML ドキュメントのクエリを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="674ca-117">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="674ca-118">詳細については、「 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="674ca-118">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="674ca-119">子要素</span><span class="sxs-lookup"><span data-stu-id="674ca-119">Child Elements</span></span>  
 <span data-ttu-id="674ca-120">なし。</span><span class="sxs-lookup"><span data-stu-id="674ca-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="674ca-121">親要素</span><span class="sxs-lookup"><span data-stu-id="674ca-121">Parent Elements</span></span>  
  
|<span data-ttu-id="674ca-122">要素</span><span class="sxs-lookup"><span data-stu-id="674ca-122">Element</span></span>|<span data-ttu-id="674ca-123">説明</span><span class="sxs-lookup"><span data-stu-id="674ca-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="674ca-124">\<filters></span><span class="sxs-lookup"><span data-stu-id="674ca-124">\<filters></span></span>](filters.md)|<span data-ttu-id="674ca-125">ログに記録されるメッセージの種類を制御する XPath フィルターのコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="674ca-125">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="674ca-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="674ca-126">Remarks</span></span>  
 <span data-ttu-id="674ca-127">フィルターは、`logMessagesAtTransportLevel` を `true` に設定することによって指定されるトランスポート層でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="674ca-127">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="674ca-128">サービス レベルおよび形式が正しくないメッセージ ログ記録は、フィルターの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="674ca-128">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="674ca-129">コレクションにフィルターを追加するには、`add` を使用します。</span><span class="sxs-lookup"><span data-stu-id="674ca-129">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="674ca-130">1 つ以上のフィルターを定義した場合は、少なくとも 1 つのフィルターと一致するメッセージだけが記録されます。</span><span class="sxs-lookup"><span data-stu-id="674ca-130">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="674ca-131">フィルターを定義しなかった場合は、すべてのメッセージが通過します。</span><span class="sxs-lookup"><span data-stu-id="674ca-131">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="674ca-132">フィルターは、完全な XPath 構文をサポートし、構成ファイルでの出現順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="674ca-132">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="674ca-133">フィルターが構文的に正しくない場合は、構成例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="674ca-133">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="674ca-134">SOAP ヘッダー セクションがあるメッセージだけを記録するフィルターの設定方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="674ca-134">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="674ca-135">例</span><span class="sxs-lookup"><span data-stu-id="674ca-135">Example</span></span>  
 <span data-ttu-id="674ca-136">SOAP ヘッダー セクションがあるメッセージだけを記録するフィルターの設定方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="674ca-136">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="674ca-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="674ca-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="674ca-138">メッセージ ログの構成</span><span class="sxs-lookup"><span data-stu-id="674ca-138">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="674ca-139">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="674ca-139">\<messageLogging></span></span>](messagelogging.md)

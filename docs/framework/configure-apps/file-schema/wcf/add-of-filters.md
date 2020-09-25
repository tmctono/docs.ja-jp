---
title: <add> の <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: c1de0605bc8afc502a85d9b2917b975ee45a3d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201656"
---
# <a name="add-of-filters"></a><span data-ttu-id="bb00b-102">\<add> の \<filters></span><span class="sxs-lookup"><span data-stu-id="bb00b-102">\<add> of \<filters></span></span>

<span data-ttu-id="bb00b-103">ログに記録するメッセージの種類を指定する XPath フィルター。</span><span class="sxs-lookup"><span data-stu-id="bb00b-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="bb00b-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb00b-104">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb00b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bb00b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bb00b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb00b-107">属性</span><span class="sxs-lookup"><span data-stu-id="bb00b-107">Attributes</span></span>  
  
|<span data-ttu-id="bb00b-108">属性</span><span class="sxs-lookup"><span data-stu-id="bb00b-108">Attribute</span></span>|<span data-ttu-id="bb00b-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="bb00b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb00b-110">filter</span><span class="sxs-lookup"><span data-stu-id="bb00b-110">filter</span></span>|<span data-ttu-id="bb00b-111">XPath 1.0 の式によって定義される、XML ドキュメントのクエリを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bb00b-111">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="bb00b-112">詳細については、「<xref:System.ServiceModel.Dispatcher.XPathMessageFilter>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb00b-112">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb00b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="bb00b-113">Child Elements</span></span>  

 <span data-ttu-id="bb00b-114">なし。</span><span class="sxs-lookup"><span data-stu-id="bb00b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb00b-115">親要素</span><span class="sxs-lookup"><span data-stu-id="bb00b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bb00b-116">要素</span><span class="sxs-lookup"><span data-stu-id="bb00b-116">Element</span></span>|<span data-ttu-id="bb00b-117">説明</span><span class="sxs-lookup"><span data-stu-id="bb00b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="bb00b-118">ログに記録されるメッセージの種類を制御する XPath フィルターのコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-118">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb00b-119">解説</span><span class="sxs-lookup"><span data-stu-id="bb00b-119">Remarks</span></span>  

 <span data-ttu-id="bb00b-120">フィルターは、`logMessagesAtTransportLevel` を `true` に設定することによって指定されるトランスポート層でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="bb00b-120">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="bb00b-121">サービス レベルおよび形式が正しくないメッセージ ログ記録は、フィルターの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="bb00b-121">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="bb00b-122">コレクションにフィルターを追加するには、`add` を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-122">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="bb00b-123">1 つ以上のフィルターを定義した場合は、少なくとも 1 つのフィルターと一致するメッセージだけが記録されます。</span><span class="sxs-lookup"><span data-stu-id="bb00b-123">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="bb00b-124">フィルターを定義しなかった場合は、すべてのメッセージが通過します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-124">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="bb00b-125">フィルターは、完全な XPath 構文をサポートし、構成ファイルでの出現順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bb00b-125">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="bb00b-126">フィルターが構文的に正しくない場合は、構成例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-126">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="bb00b-127">SOAP ヘッダー セクションがあるメッセージだけを記録するフィルターの設定方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-127">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb00b-128">例</span><span class="sxs-lookup"><span data-stu-id="bb00b-128">Example</span></span>  

 <span data-ttu-id="bb00b-129">SOAP ヘッダー セクションがあるメッセージだけを記録するフィルターの設定方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb00b-129">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb00b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb00b-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="bb00b-131">メッセージ ログの構成</span><span class="sxs-lookup"><span data-stu-id="bb00b-131">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)

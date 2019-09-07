---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400021"
---
# <a name="protocolmapping"></a><span data-ttu-id="94916-101">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="94916-101">\<protocolMapping></span></span>
<span data-ttu-id="94916-102">トランスポートプロトコルスキーム (http、net.tcp、net.pipe など) と WCF バインドとの一連の既定のプロトコルマッピングを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="94916-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="94916-103">実行時に既定のエンドポイントを作成すると、Windows Communication Foundation (WCF) によって、構成済みのマッピングが参照され、特定のベースアドレスに対して使用するバインドが決定されます。</span><span class="sxs-lookup"><span data-stu-id="94916-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="94916-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="94916-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="94916-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="94916-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="94916-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="94916-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94916-107">構文</span><span class="sxs-lookup"><span data-stu-id="94916-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94916-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="94916-108">Attributes and Elements</span></span>  
 <span data-ttu-id="94916-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="94916-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94916-110">属性</span><span class="sxs-lookup"><span data-stu-id="94916-110">Attributes</span></span>  
 <span data-ttu-id="94916-111">なし。</span><span class="sxs-lookup"><span data-stu-id="94916-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94916-112">子要素</span><span class="sxs-lookup"><span data-stu-id="94916-112">Child Elements</span></span>  
  
|<span data-ttu-id="94916-113">要素</span><span class="sxs-lookup"><span data-stu-id="94916-113">Element</span></span>|<span data-ttu-id="94916-114">説明</span><span class="sxs-lookup"><span data-stu-id="94916-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94916-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="94916-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="94916-116">トランスポートプロトコルスキーム (http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコルマッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94916-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94916-117">親要素</span><span class="sxs-lookup"><span data-stu-id="94916-117">Parent Elements</span></span>  
  
|<span data-ttu-id="94916-118">要素</span><span class="sxs-lookup"><span data-stu-id="94916-118">Element</span></span>|<span data-ttu-id="94916-119">説明</span><span class="sxs-lookup"><span data-stu-id="94916-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94916-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="94916-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="94916-121">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="94916-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94916-122">例</span><span class="sxs-lookup"><span data-stu-id="94916-122">Example</span></span>  
 <span data-ttu-id="94916-123">次の構成例は、machine.config ファイル内の既定のプロトコル マッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="94916-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="94916-124">machine.config ファイルを変更することで、既定のマッピングをコンピューター レベルでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="94916-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="94916-125">または、アプリケーションのスコープ内だけでオーバーライドする場合は、アプリケーション構成ファイルのこのセクションをオーバーライドし、各プロトコル スキームのマッピングを変更できます。</span><span class="sxs-lookup"><span data-stu-id="94916-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="94916-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="94916-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>

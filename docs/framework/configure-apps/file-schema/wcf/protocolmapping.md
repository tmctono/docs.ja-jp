---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: e26044340bda84fe38b7e286edf833affa94b86c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118216"
---
# <a name="protocolmapping"></a><span data-ttu-id="7735d-101">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="7735d-101">\<protocolMapping></span></span>
<span data-ttu-id="7735d-102">トランスポート プロトコル スキーム (など、http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコル マッピングのセットを定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7735d-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="7735d-103">実行時に既定のエンドポイントを作成するときに、Windows Communication Foundation (WCF) が構成済みのマッピングではされ、特定に使用するバインディングをベース アドレスを決定します。</span><span class="sxs-lookup"><span data-stu-id="7735d-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="7735d-104">**\<system.serviceModel>**</span><span class="sxs-lookup"><span data-stu-id="7735d-104">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="7735d-105">&nbsp;&nbsp;**\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="7735d-105">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7735d-106">構文</span><span class="sxs-lookup"><span data-stu-id="7735d-106">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7735d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7735d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7735d-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7735d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7735d-109">属性</span><span class="sxs-lookup"><span data-stu-id="7735d-109">Attributes</span></span>  
 <span data-ttu-id="7735d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7735d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7735d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7735d-111">Child Elements</span></span>  
  
|<span data-ttu-id="7735d-112">要素</span><span class="sxs-lookup"><span data-stu-id="7735d-112">Element</span></span>|<span data-ttu-id="7735d-113">説明</span><span class="sxs-lookup"><span data-stu-id="7735d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7735d-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="7735d-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="7735d-115">トランスポート プロトコル スキーム (など、http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコル マッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7735d-115">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7735d-116">親要素</span><span class="sxs-lookup"><span data-stu-id="7735d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7735d-117">要素</span><span class="sxs-lookup"><span data-stu-id="7735d-117">Element</span></span>|<span data-ttu-id="7735d-118">説明</span><span class="sxs-lookup"><span data-stu-id="7735d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7735d-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7735d-119">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="7735d-120">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7735d-120">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7735d-121">例</span><span class="sxs-lookup"><span data-stu-id="7735d-121">Example</span></span>  
 <span data-ttu-id="7735d-122">次の構成例は、machine.config ファイル内の既定のプロトコル マッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="7735d-122">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="7735d-123">machine.config ファイルを変更することで、既定のマッピングをコンピューター レベルでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="7735d-123">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="7735d-124">または、アプリケーションのスコープ内だけでオーバーライドする場合は、アプリケーション構成ファイルのこのセクションをオーバーライドし、各プロトコル スキームのマッピングを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7735d-124">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7735d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7735d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>

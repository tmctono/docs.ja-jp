---
title: <add> の <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850385"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="ec8c9-102">\<protocolmapping > \<の > を追加します</span><span class="sxs-lookup"><span data-stu-id="ec8c9-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="ec8c9-103">トランスポートプロトコルスキーム (http、net.tcp、net.pipe など) と Windows Communication Foundation (WCF) バインドとの間の既定のプロトコルマッピングを表します。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="ec8c9-104">実行時に既定のエンドポイントを作成する場合、WCF は構成されたマッピングを調べ、特定のベースアドレスに使用するバインドを決定します。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="ec8c9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec8c9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ec8c9-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ec8c9-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ec8c9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<protocolMapping >** ](protocolmapping.md)</span><span class="sxs-lookup"><span data-stu-id="ec8c9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)</span></span>\
<span data-ttu-id="ec8c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="ec8c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8c9-109">構文</span><span class="sxs-lookup"><span data-stu-id="ec8c9-109">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec8c9-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ec8c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ec8c9-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec8c9-112">属性</span><span class="sxs-lookup"><span data-stu-id="ec8c9-112">Attributes</span></span>  
  
|<span data-ttu-id="ec8c9-113">要素</span><span class="sxs-lookup"><span data-stu-id="ec8c9-113">Element</span></span>|<span data-ttu-id="ec8c9-114">説明</span><span class="sxs-lookup"><span data-stu-id="ec8c9-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec8c9-115">バインド</span><span class="sxs-lookup"><span data-stu-id="ec8c9-115">binding</span></span>|<span data-ttu-id="ec8c9-116">既定のエンドポイントを作成するときにエンドポイントに使用されるバインディングの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-116">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="ec8c9-117">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec8c9-117">bindingConfiguration</span></span>|<span data-ttu-id="ec8c9-118">参照されるバインディング構成セクションの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-118">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="ec8c9-119">scheme</span><span class="sxs-lookup"><span data-stu-id="ec8c9-119">scheme</span></span>|<span data-ttu-id="ec8c9-120">既定のエンドポイントに使用されるトランスポート プロトコル スキーム。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-120">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec8c9-121">子要素</span><span class="sxs-lookup"><span data-stu-id="ec8c9-121">Child Elements</span></span>  
 <span data-ttu-id="ec8c9-122">なし。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec8c9-123">親要素</span><span class="sxs-lookup"><span data-stu-id="ec8c9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ec8c9-124">要素</span><span class="sxs-lookup"><span data-stu-id="ec8c9-124">Element</span></span>|<span data-ttu-id="ec8c9-125">説明</span><span class="sxs-lookup"><span data-stu-id="ec8c9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec8c9-126">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="ec8c9-126">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="ec8c9-127">トランスポートプロトコルスキーム (http、net.tcp、net.pipe など) と Windows Communication Foundation (WCF) バインド間の既定のプロトコルマッピングを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-127">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ec8c9-128">例</span><span class="sxs-lookup"><span data-stu-id="ec8c9-128">Example</span></span>  
 <span data-ttu-id="ec8c9-129">次の構成例は、machine.config ファイル内の既定のプロトコル マッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-129">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="ec8c9-130">machine.config ファイルを変更することで、既定のマッピングをコンピューター レベルでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-130">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="ec8c9-131">または、アプリケーションのスコープ内だけでオーバーライドする場合は、アプリケーション構成ファイルのこのセクションをオーバーライドし、各プロトコル スキームのマッピングを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ec8c9-131">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec8c9-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec8c9-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>

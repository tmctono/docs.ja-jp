---
title: <add> の <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 46ba21b65f524f88bfce81739f0cd73040a2ad45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205010"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="d4aa6-102">\<add> の \<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="d4aa6-102">\<add> of \<protocolMapping></span></span>

<span data-ttu-id="d4aa6-103">トランスポートプロトコルスキーム (http、net.tcp、net.pipe など) と Windows Communication Foundation (WCF) バインドとの間の既定のプロトコルマッピングを表します。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="d4aa6-104">実行時に既定のエンドポイントを作成する場合、WCF は構成されたマッピングを調べ、特定のベースアドレスに使用するバインドを決定します。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d4aa6-105">構文</span><span class="sxs-lookup"><span data-stu-id="d4aa6-105">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4aa6-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4aa6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d4aa6-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4aa6-108">属性</span><span class="sxs-lookup"><span data-stu-id="d4aa6-108">Attributes</span></span>  
  
|<span data-ttu-id="d4aa6-109">要素</span><span class="sxs-lookup"><span data-stu-id="d4aa6-109">Element</span></span>|<span data-ttu-id="d4aa6-110">説明</span><span class="sxs-lookup"><span data-stu-id="d4aa6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4aa6-111">binding</span><span class="sxs-lookup"><span data-stu-id="d4aa6-111">binding</span></span>|<span data-ttu-id="d4aa6-112">既定のエンドポイントを作成するときにエンドポイントに使用されるバインディングの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-112">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="d4aa6-113">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4aa6-113">bindingConfiguration</span></span>|<span data-ttu-id="d4aa6-114">参照されるバインディング構成セクションの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-114">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="d4aa6-115">scheme</span><span class="sxs-lookup"><span data-stu-id="d4aa6-115">scheme</span></span>|<span data-ttu-id="d4aa6-116">既定のエンドポイントに使用されるトランスポート プロトコル スキーム。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-116">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4aa6-117">子要素</span><span class="sxs-lookup"><span data-stu-id="d4aa6-117">Child Elements</span></span>  

 <span data-ttu-id="d4aa6-118">なし。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4aa6-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d4aa6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d4aa6-120">要素</span><span class="sxs-lookup"><span data-stu-id="d4aa6-120">Element</span></span>|<span data-ttu-id="d4aa6-121">説明</span><span class="sxs-lookup"><span data-stu-id="d4aa6-121">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="d4aa6-122">トランスポートプロトコルスキーム (http、net.tcp、net.pipe など) と Windows Communication Foundation (WCF) バインド間の既定のプロトコルマッピングを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-122">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4aa6-123">例</span><span class="sxs-lookup"><span data-stu-id="d4aa6-123">Example</span></span>  

 <span data-ttu-id="d4aa6-124">次の構成例は、machine.config ファイル内の既定のプロトコル マッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-124">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="d4aa6-125">machine.config ファイルを変更することで、既定のマッピングをコンピューター レベルでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-125">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="d4aa6-126">または、アプリケーションのスコープ内だけでオーバーライドする場合は、アプリケーション構成ファイルのこのセクションをオーバーライドし、各プロトコル スキームのマッピングを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d4aa6-126">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d4aa6-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4aa6-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>

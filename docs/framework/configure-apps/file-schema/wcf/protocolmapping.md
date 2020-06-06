---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400021"
---
# \<protocolMapping>
<span data-ttu-id="a695e-101">トランスポート プロトコル スキーム (http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコル マッピング セットを定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="a695e-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="a695e-102">実行時に既定のエンドポイントを作成すると、Windows Communication Foundation (WCF) によって、構成済みのマッピングが参照され、特定のベースアドレスに対して使用するバインドが決定されます。</span><span class="sxs-lookup"><span data-stu-id="a695e-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="a695e-103">構文</span><span class="sxs-lookup"><span data-stu-id="a695e-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a695e-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a695e-104">Attributes and Elements</span></span>  
 <span data-ttu-id="a695e-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a695e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a695e-106">属性</span><span class="sxs-lookup"><span data-stu-id="a695e-106">Attributes</span></span>  
 <span data-ttu-id="a695e-107">なし。</span><span class="sxs-lookup"><span data-stu-id="a695e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a695e-108">子要素</span><span class="sxs-lookup"><span data-stu-id="a695e-108">Child Elements</span></span>  
  
|<span data-ttu-id="a695e-109">要素</span><span class="sxs-lookup"><span data-stu-id="a695e-109">Element</span></span>|<span data-ttu-id="a695e-110">説明</span><span class="sxs-lookup"><span data-stu-id="a695e-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="a695e-111">トランスポート プロトコル スキーム (http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコル マッピングを格納します。</span><span class="sxs-lookup"><span data-stu-id="a695e-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a695e-112">親要素</span><span class="sxs-lookup"><span data-stu-id="a695e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a695e-113">要素</span><span class="sxs-lookup"><span data-stu-id="a695e-113">Element</span></span>|<span data-ttu-id="a695e-114">説明</span><span class="sxs-lookup"><span data-stu-id="a695e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="a695e-115">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a695e-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a695e-116">例</span><span class="sxs-lookup"><span data-stu-id="a695e-116">Example</span></span>  
 <span data-ttu-id="a695e-117">次の構成例は、machine.config ファイル内の既定のプロトコル マッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="a695e-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="a695e-118">machine.config ファイルを変更することで、既定のマッピングをコンピューター レベルでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="a695e-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="a695e-119">または、アプリケーションのスコープ内だけでオーバーライドする場合は、アプリケーション構成ファイルのこのセクションをオーバーライドし、各プロトコル スキームのマッピングを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a695e-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a695e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a695e-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>

---
title: <add> の <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398386"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="b0e1f-102">\<add> の \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="b0e1f-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="b0e1f-103">WCF サービスをホストし、共有サービスへの接続アクセスが許可されているプロセスのユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b0e1f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0e1f-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0e1f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b0e1f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b0e1f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0e1f-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0e1f-107">Attributes</span></span>  
  
|<span data-ttu-id="b0e1f-108">属性</span><span class="sxs-lookup"><span data-stu-id="b0e1f-108">Attribute</span></span>|<span data-ttu-id="b0e1f-109">説明</span><span class="sxs-lookup"><span data-stu-id="b0e1f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0e1f-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b0e1f-110">securityIdentifier</span></span>|<span data-ttu-id="b0e1f-111">ユーザー アカウントの識別に使用される一意の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="b0e1f-112">既定値は LocalSystem、Administrators、NS、LS、および IIS_USRS です。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0e1f-113">子要素</span><span class="sxs-lookup"><span data-stu-id="b0e1f-113">Child Elements</span></span>  
 <span data-ttu-id="b0e1f-114">なし。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0e1f-115">親要素</span><span class="sxs-lookup"><span data-stu-id="b0e1f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b0e1f-116">要素</span><span class="sxs-lookup"><span data-stu-id="b0e1f-116">Element</span></span>|<span data-ttu-id="b0e1f-117">Description</span><span class="sxs-lookup"><span data-stu-id="b0e1f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="b0e1f-118">`securityIdentifier`WCF サービスをホストするプロセスのユーザーアカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b0e1f-119">例</span><span class="sxs-lookup"><span data-stu-id="b0e1f-119">Example</span></span>  
 <span data-ttu-id="b0e1f-120">次の構成例は、このコレクションにユーザー アカウントの 5 つの既定の識別子を追加します。</span><span class="sxs-lookup"><span data-stu-id="b0e1f-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="b0e1f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0e1f-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>

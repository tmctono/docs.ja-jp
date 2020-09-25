---
title: <add> の <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: cd4b9fd02eee2de1d0e8be185ffb69c0eae1cd58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181727"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="3ec2d-102">\<add> の \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="3ec2d-102">\<add> of \<allowAccounts></span></span>

<span data-ttu-id="3ec2d-103">WCF サービスをホストし、共有サービスへの接続アクセスが許可されているプロセスのユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3ec2d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ec2d-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ec2d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ec2d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3ec2d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ec2d-107">属性</span><span class="sxs-lookup"><span data-stu-id="3ec2d-107">Attributes</span></span>  
  
|<span data-ttu-id="3ec2d-108">属性</span><span class="sxs-lookup"><span data-stu-id="3ec2d-108">Attribute</span></span>|<span data-ttu-id="3ec2d-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="3ec2d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ec2d-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="3ec2d-110">securityIdentifier</span></span>|<span data-ttu-id="3ec2d-111">ユーザー アカウントの識別に使用される一意の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="3ec2d-112">既定値は LocalSystem、Administrators、NS、LS、および IIS_USRS です。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ec2d-113">子要素</span><span class="sxs-lookup"><span data-stu-id="3ec2d-113">Child Elements</span></span>  

 <span data-ttu-id="3ec2d-114">なし。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ec2d-115">親要素</span><span class="sxs-lookup"><span data-stu-id="3ec2d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3ec2d-116">要素</span><span class="sxs-lookup"><span data-stu-id="3ec2d-116">Element</span></span>|<span data-ttu-id="3ec2d-117">説明</span><span class="sxs-lookup"><span data-stu-id="3ec2d-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="3ec2d-118">`securityIdentifier`WCF サービスをホストするプロセスのユーザーアカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ec2d-119">例</span><span class="sxs-lookup"><span data-stu-id="3ec2d-119">Example</span></span>  

 <span data-ttu-id="3ec2d-120">次の構成例は、このコレクションにユーザー アカウントの 5 つの既定の識別子を追加します。</span><span class="sxs-lookup"><span data-stu-id="3ec2d-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ec2d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ec2d-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>

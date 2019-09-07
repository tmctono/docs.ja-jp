---
title: <add> の <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398386"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="1bbac-102">\<allowaccounts の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="1bbac-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="1bbac-103">WCF サービスをホストし、共有サービスへの接続アクセスが許可されているプロセスのユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bbac-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="1bbac-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bbac-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1bbac-105">&nbsp;&nbsp;[ **\<System.servicemodel. activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="1bbac-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="1bbac-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<net.pipe >** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="1bbac-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="1bbac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<allowAccounts >** ](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="1bbac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="1bbac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="1bbac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bbac-109">構文</span><span class="sxs-lookup"><span data-stu-id="1bbac-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bbac-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bbac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1bbac-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bbac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bbac-112">属性</span><span class="sxs-lookup"><span data-stu-id="1bbac-112">Attributes</span></span>  
  
|<span data-ttu-id="1bbac-113">属性</span><span class="sxs-lookup"><span data-stu-id="1bbac-113">Attribute</span></span>|<span data-ttu-id="1bbac-114">説明</span><span class="sxs-lookup"><span data-stu-id="1bbac-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bbac-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="1bbac-115">securityIdentifier</span></span>|<span data-ttu-id="1bbac-116">ユーザー アカウントの識別に使用される一意の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1bbac-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="1bbac-117">既定値は LocalSystem、Administrators、NS、LS、および IIS_USRS です。</span><span class="sxs-lookup"><span data-stu-id="1bbac-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bbac-118">子要素</span><span class="sxs-lookup"><span data-stu-id="1bbac-118">Child Elements</span></span>  
 <span data-ttu-id="1bbac-119">なし。</span><span class="sxs-lookup"><span data-stu-id="1bbac-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bbac-120">親要素</span><span class="sxs-lookup"><span data-stu-id="1bbac-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1bbac-121">要素</span><span class="sxs-lookup"><span data-stu-id="1bbac-121">Element</span></span>|<span data-ttu-id="1bbac-122">説明</span><span class="sxs-lookup"><span data-stu-id="1bbac-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bbac-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="1bbac-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="1bbac-124">WCF サービスをホストするプロセスのユーザー `securityIdentifier`アカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="1bbac-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1bbac-125">例</span><span class="sxs-lookup"><span data-stu-id="1bbac-125">Example</span></span>  
 <span data-ttu-id="1bbac-126">次の構成例は、このコレクションにユーザー アカウントの 5 つの既定の識別子を追加します。</span><span class="sxs-lookup"><span data-stu-id="1bbac-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1bbac-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bbac-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>

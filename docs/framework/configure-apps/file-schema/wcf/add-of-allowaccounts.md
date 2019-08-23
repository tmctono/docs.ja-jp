---
title: <add> の <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1ed0b5025ab969c45d7440f2a209426c5c87f549
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920288"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="65897-102">\<allowaccounts の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="65897-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="65897-103">WCF サービスをホストし、共有サービスへの接続アクセスが許可されているプロセスのユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="65897-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="65897-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="65897-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65897-105">構文</span><span class="sxs-lookup"><span data-stu-id="65897-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65897-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65897-106">Attributes and Elements</span></span>  
 <span data-ttu-id="65897-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="65897-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65897-108">属性</span><span class="sxs-lookup"><span data-stu-id="65897-108">Attributes</span></span>  
  
|<span data-ttu-id="65897-109">属性</span><span class="sxs-lookup"><span data-stu-id="65897-109">Attribute</span></span>|<span data-ttu-id="65897-110">説明</span><span class="sxs-lookup"><span data-stu-id="65897-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65897-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="65897-111">securityIdentifier</span></span>|<span data-ttu-id="65897-112">ユーザー アカウントの識別に使用される一意の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="65897-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="65897-113">既定値は LocalSystem、Administrators、NS、LS、および IIS_USRS です。</span><span class="sxs-lookup"><span data-stu-id="65897-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65897-114">子要素</span><span class="sxs-lookup"><span data-stu-id="65897-114">Child Elements</span></span>  
 <span data-ttu-id="65897-115">なし。</span><span class="sxs-lookup"><span data-stu-id="65897-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65897-116">親要素</span><span class="sxs-lookup"><span data-stu-id="65897-116">Parent Elements</span></span>  
  
|<span data-ttu-id="65897-117">要素</span><span class="sxs-lookup"><span data-stu-id="65897-117">Element</span></span>|<span data-ttu-id="65897-118">説明</span><span class="sxs-lookup"><span data-stu-id="65897-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65897-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="65897-119">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="65897-120">WCF サービスをホストするプロセスのユーザー `securityIdentifier`アカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="65897-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="65897-121">例</span><span class="sxs-lookup"><span data-stu-id="65897-121">Example</span></span>  
 <span data-ttu-id="65897-122">次の構成例は、このコレクションにユーザー アカウントの 5 つの既定の識別子を追加します。</span><span class="sxs-lookup"><span data-stu-id="65897-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65897-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="65897-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>

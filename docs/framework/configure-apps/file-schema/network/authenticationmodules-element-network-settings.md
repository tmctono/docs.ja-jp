---
title: <authenticationModules> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 8878bcbdf8b3613677231db3e91a6d71dfa10bae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674715"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="d3570-102">\<authenticationModules > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="d3570-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="d3570-103">ネットワーク要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3570-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="d3570-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d3570-104">\<configuration></span></span>  
<span data-ttu-id="d3570-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d3570-105">\<system.net></span></span>  
<span data-ttu-id="d3570-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="d3570-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3570-107">構文</span><span class="sxs-lookup"><span data-stu-id="d3570-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3570-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d3570-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d3570-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3570-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3570-110">属性</span><span class="sxs-lookup"><span data-stu-id="d3570-110">Attributes</span></span>  
 <span data-ttu-id="d3570-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d3570-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d3570-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d3570-112">Child Elements</span></span>  
  
|<span data-ttu-id="d3570-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="d3570-113">**Element**</span></span>|<span data-ttu-id="d3570-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="d3570-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d3570-115">add</span><span class="sxs-lookup"><span data-stu-id="d3570-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="d3570-116">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="d3570-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="d3570-117">clear</span><span class="sxs-lookup"><span data-stu-id="d3570-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="d3570-118">アプリケーションからのすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d3570-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="d3570-119">remove</span><span class="sxs-lookup"><span data-stu-id="d3570-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="d3570-120">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d3570-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3570-121">親要素</span><span class="sxs-lookup"><span data-stu-id="d3570-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d3570-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="d3570-122">**Element**</span></span>|<span data-ttu-id="d3570-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="d3570-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d3570-124">system.net</span><span class="sxs-lookup"><span data-stu-id="d3570-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="d3570-125">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3570-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3570-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3570-126">Remarks</span></span>  
 <span data-ttu-id="d3570-127">`authenticationModule`要素は、サーバーと認証プロセスを実行する認証モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3570-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="d3570-128">認証モジュールを実装する必要があります、<xref:System.Net.IAuthenticationModule>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d3570-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d3570-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d3570-129">Configuration Files</span></span>  
 <span data-ttu-id="d3570-130">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3570-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3570-131">例</span><span class="sxs-lookup"><span data-stu-id="d3570-131">Example</span></span>  
 <span data-ttu-id="d3570-132">次の例では、認証モジュールを有効します。</span><span class="sxs-lookup"><span data-stu-id="d3570-132">The following example enables an authentication module.</span></span> <span data-ttu-id="d3570-133">指定したモジュールの正しい値で、バージョンおよび PublicKeyToken の値を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3570-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3570-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3570-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="d3570-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d3570-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

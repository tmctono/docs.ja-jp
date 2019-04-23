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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143339"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="85cb3-102">\<authenticationModules > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="85cb3-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="85cb3-103">ネットワーク要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="85cb3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="85cb3-104">\<configuration></span></span>  
<span data-ttu-id="85cb3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="85cb3-105">\<system.net></span></span>  
<span data-ttu-id="85cb3-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="85cb3-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85cb3-107">構文</span><span class="sxs-lookup"><span data-stu-id="85cb3-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85cb3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85cb3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="85cb3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85cb3-110">属性</span><span class="sxs-lookup"><span data-stu-id="85cb3-110">Attributes</span></span>  
 <span data-ttu-id="85cb3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="85cb3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85cb3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="85cb3-112">Child Elements</span></span>  
  
|<span data-ttu-id="85cb3-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="85cb3-113">**Element**</span></span>|<span data-ttu-id="85cb3-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="85cb3-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="85cb3-115">add</span><span class="sxs-lookup"><span data-stu-id="85cb3-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="85cb3-116">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="85cb3-117">clear</span><span class="sxs-lookup"><span data-stu-id="85cb3-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="85cb3-118">アプリケーションからのすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="85cb3-119">remove</span><span class="sxs-lookup"><span data-stu-id="85cb3-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="85cb3-120">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85cb3-121">親要素</span><span class="sxs-lookup"><span data-stu-id="85cb3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="85cb3-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="85cb3-122">**Element**</span></span>|<span data-ttu-id="85cb3-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="85cb3-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="85cb3-124">system.net</span><span class="sxs-lookup"><span data-stu-id="85cb3-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="85cb3-125">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85cb3-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85cb3-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="85cb3-126">Remarks</span></span>  
 <span data-ttu-id="85cb3-127">`authenticationModule`要素は、サーバーと認証プロセスを実行する認証モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="85cb3-128">認証モジュールを実装する必要があります、<xref:System.Net.IAuthenticationModule>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="85cb3-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="85cb3-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="85cb3-129">Configuration Files</span></span>  
 <span data-ttu-id="85cb3-130">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="85cb3-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85cb3-131">例</span><span class="sxs-lookup"><span data-stu-id="85cb3-131">Example</span></span>  
 <span data-ttu-id="85cb3-132">次の例では、認証モジュールを有効します。</span><span class="sxs-lookup"><span data-stu-id="85cb3-132">The following example enables an authentication module.</span></span> <span data-ttu-id="85cb3-133">指定したモジュールの正しい値で、バージョンおよび PublicKeyToken の値を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="85cb3-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="85cb3-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="85cb3-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="85cb3-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="85cb3-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

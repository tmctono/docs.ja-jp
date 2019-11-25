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
ms.openlocfilehash: bacaaf92464a355804a9ea8307f6e6f1caac1f05
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087613"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="675e3-102">\<authenticationModules > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="675e3-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="675e3-103">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="675e3-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="675e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="675e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="675e3-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="675e3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="675e3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<authenticationModules >**</span><span class="sxs-lookup"><span data-stu-id="675e3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="675e3-107">構文</span><span class="sxs-lookup"><span data-stu-id="675e3-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="675e3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="675e3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="675e3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="675e3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="675e3-110">属性</span><span class="sxs-lookup"><span data-stu-id="675e3-110">Attributes</span></span>  
 <span data-ttu-id="675e3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="675e3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="675e3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="675e3-112">Child Elements</span></span>  
  
|<span data-ttu-id="675e3-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="675e3-113">**Element**</span></span>|<span data-ttu-id="675e3-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="675e3-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="675e3-115">add</span><span class="sxs-lookup"><span data-stu-id="675e3-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="675e3-116">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="675e3-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="675e3-117">clear</span><span class="sxs-lookup"><span data-stu-id="675e3-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="675e3-118">アプリケーションからすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="675e3-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="675e3-119">remove</span><span class="sxs-lookup"><span data-stu-id="675e3-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="675e3-120">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="675e3-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="675e3-121">親要素</span><span class="sxs-lookup"><span data-stu-id="675e3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="675e3-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="675e3-122">**Element**</span></span>|<span data-ttu-id="675e3-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="675e3-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="675e3-124">system.net</span><span class="sxs-lookup"><span data-stu-id="675e3-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="675e3-125">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="675e3-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="675e3-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="675e3-126">Remarks</span></span>  
 <span data-ttu-id="675e3-127">`authenticationModule` 要素は、サーバーとの認証プロセスを実行する認証モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="675e3-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="675e3-128">認証モジュールは、<xref:System.Net.IAuthenticationModule> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="675e3-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="675e3-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="675e3-129">Configuration Files</span></span>  
 <span data-ttu-id="675e3-130">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="675e3-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="675e3-131">例</span><span class="sxs-lookup"><span data-stu-id="675e3-131">Example</span></span>  
 <span data-ttu-id="675e3-132">次の例では、認証モジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="675e3-132">The following example enables an authentication module.</span></span> <span data-ttu-id="675e3-133">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="675e3-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="675e3-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="675e3-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="675e3-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="675e3-135">Network Settings Schema</span></span>](index.md)

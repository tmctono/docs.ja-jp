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
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154973"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="98bee-102">\<authenticationModules> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="98bee-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="98bee-103">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="98bee-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="98bee-104">構文</span><span class="sxs-lookup"><span data-stu-id="98bee-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98bee-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="98bee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="98bee-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="98bee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98bee-107">属性</span><span class="sxs-lookup"><span data-stu-id="98bee-107">Attributes</span></span>  
 <span data-ttu-id="98bee-108">なし。</span><span class="sxs-lookup"><span data-stu-id="98bee-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98bee-109">子要素</span><span class="sxs-lookup"><span data-stu-id="98bee-109">Child Elements</span></span>  
  
|<span data-ttu-id="98bee-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="98bee-110">**Element**</span></span>|<span data-ttu-id="98bee-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="98bee-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="98bee-112">add</span><span class="sxs-lookup"><span data-stu-id="98bee-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="98bee-113">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="98bee-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="98bee-114">オフ</span><span class="sxs-lookup"><span data-stu-id="98bee-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="98bee-115">アプリケーションからすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="98bee-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="98bee-116">remove</span><span class="sxs-lookup"><span data-stu-id="98bee-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="98bee-117">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="98bee-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98bee-118">親要素</span><span class="sxs-lookup"><span data-stu-id="98bee-118">Parent Elements</span></span>  
  
|<span data-ttu-id="98bee-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="98bee-119">**Element**</span></span>|<span data-ttu-id="98bee-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="98bee-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="98bee-121">system.net</span><span class="sxs-lookup"><span data-stu-id="98bee-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="98bee-122">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="98bee-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98bee-123">解説</span><span class="sxs-lookup"><span data-stu-id="98bee-123">Remarks</span></span>  
 <span data-ttu-id="98bee-124">要素は、 `authenticationModule` サーバーとの認証プロセスを実行する認証モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="98bee-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="98bee-125">認証モジュールは、インターフェイスを実装する必要があり <xref:System.Net.IAuthenticationModule> ます。</span><span class="sxs-lookup"><span data-stu-id="98bee-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="98bee-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="98bee-126">Configuration Files</span></span>  
 <span data-ttu-id="98bee-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="98bee-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98bee-128">例</span><span class="sxs-lookup"><span data-stu-id="98bee-128">Example</span></span>  
 <span data-ttu-id="98bee-129">次の例では、認証モジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="98bee-129">The following example enables an authentication module.</span></span> <span data-ttu-id="98bee-130">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="98bee-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98bee-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="98bee-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="98bee-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="98bee-132">Network Settings Schema</span></span>](index.md)

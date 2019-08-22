---
title: <module> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 851a63b41dfb5d3b4058e1373148f48d47d9d6ae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664069"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="3afd3-102">\<module> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="3afd3-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="3afd3-103">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3afd3-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="3afd3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3afd3-104">\<configuration></span></span>  
<span data-ttu-id="3afd3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3afd3-105">\<system.net></span></span>  
<span data-ttu-id="3afd3-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="3afd3-106">\<defaultProxy></span></span>  
<span data-ttu-id="3afd3-107">\<module></span><span class="sxs-lookup"><span data-stu-id="3afd3-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3afd3-108">構文</span><span class="sxs-lookup"><span data-stu-id="3afd3-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3afd3-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3afd3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3afd3-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3afd3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3afd3-111">属性</span><span class="sxs-lookup"><span data-stu-id="3afd3-111">Attributes</span></span>  
  
|<span data-ttu-id="3afd3-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="3afd3-112">**Attribute**</span></span>|<span data-ttu-id="3afd3-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="3afd3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="3afd3-114">プロキシを実装する、( <xref:System.Type.FullName%2A>プロパティによって示される) 完全修飾型名と、コンマで区切られたアセンブリ名 ( <xref:System.Reflection.Assembly.FullName%2A>プロパティによって示されます)。</span><span class="sxs-lookup"><span data-stu-id="3afd3-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3afd3-115">子要素</span><span class="sxs-lookup"><span data-stu-id="3afd3-115">Child Elements</span></span>  
 <span data-ttu-id="3afd3-116">なし。</span><span class="sxs-lookup"><span data-stu-id="3afd3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3afd3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="3afd3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3afd3-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="3afd3-118">**Element**</span></span>|<span data-ttu-id="3afd3-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="3afd3-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3afd3-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="3afd3-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="3afd3-121">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3afd3-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3afd3-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="3afd3-122">Remarks</span></span>  
 <span data-ttu-id="3afd3-123">要素`module`は、 <xref:System.Net.IWebProxy>インターフェイスを実装するプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="3afd3-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="3afd3-124">プロキシクラスを登録した`module`後、を使用して、サポートされているプロキシ経由で情報を要求できます。</span><span class="sxs-lookup"><span data-stu-id="3afd3-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="3afd3-125">`type`属性の値は、モジュールのクラス名と、対応するダイナミックリンクライブラリ (DLL) の名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afd3-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3afd3-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="3afd3-126">Configuration Files</span></span>  
 <span data-ttu-id="3afd3-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3afd3-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3afd3-128">例</span><span class="sxs-lookup"><span data-stu-id="3afd3-128">Example</span></span>  
 <span data-ttu-id="3afd3-129">次の例では、カスタムプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="3afd3-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3afd3-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3afd3-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3afd3-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3afd3-131">Network Settings Schema</span></span>](index.md)

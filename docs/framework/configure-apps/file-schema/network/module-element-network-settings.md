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
ms.openlocfilehash: ad641f93e93f627dae1c7d0bda4620093c4567b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205049"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="83aca-102">\<module> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="83aca-102">\<module> Element (Network Settings)</span></span>

<span data-ttu-id="83aca-103">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="83aca-103">Adds a new proxy module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a><span data-ttu-id="83aca-104">構文</span><span class="sxs-lookup"><span data-stu-id="83aca-104">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83aca-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="83aca-105">Attributes and Elements</span></span>  

 <span data-ttu-id="83aca-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="83aca-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83aca-107">属性</span><span class="sxs-lookup"><span data-stu-id="83aca-107">Attributes</span></span>  
  
|<span data-ttu-id="83aca-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="83aca-108">**Attribute**</span></span>|<span data-ttu-id="83aca-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="83aca-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="83aca-110">プロキシを実装する、(プロパティによって示される) 完全修飾型名 <xref:System.Type.FullName%2A> と、コンマで区切られたアセンブリ名 (プロパティによって示され <xref:System.Reflection.Assembly.FullName%2A> ます)。</span><span class="sxs-lookup"><span data-stu-id="83aca-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83aca-111">子要素</span><span class="sxs-lookup"><span data-stu-id="83aca-111">Child Elements</span></span>  

 <span data-ttu-id="83aca-112">なし。</span><span class="sxs-lookup"><span data-stu-id="83aca-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83aca-113">親要素</span><span class="sxs-lookup"><span data-stu-id="83aca-113">Parent Elements</span></span>  
  
|<span data-ttu-id="83aca-114">**要素**</span><span class="sxs-lookup"><span data-stu-id="83aca-114">**Element**</span></span>|<span data-ttu-id="83aca-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="83aca-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83aca-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="83aca-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="83aca-117">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="83aca-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83aca-118">解説</span><span class="sxs-lookup"><span data-stu-id="83aca-118">Remarks</span></span>  

 <span data-ttu-id="83aca-119">要素は、 `module` インターフェイスを実装するプロキシクラスを登録し <xref:System.Net.IWebProxy> ます。</span><span class="sxs-lookup"><span data-stu-id="83aca-119">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="83aca-120">プロキシクラスを登録した後、を `module` 使用して、サポートされているプロキシ経由で情報を要求できます。</span><span class="sxs-lookup"><span data-stu-id="83aca-120">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="83aca-121">属性の値は、 `type` モジュールのクラス名と、対応するダイナミックリンクライブラリ (DLL) の名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83aca-121">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="83aca-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="83aca-122">Configuration Files</span></span>  

 <span data-ttu-id="83aca-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="83aca-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83aca-124">例</span><span class="sxs-lookup"><span data-stu-id="83aca-124">Example</span></span>  

 <span data-ttu-id="83aca-125">次の例では、カスタムプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="83aca-125">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83aca-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="83aca-126">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="83aca-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="83aca-127">Network Settings Schema</span></span>](index.md)

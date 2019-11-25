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
ms.openlocfilehash: 78f6418160b80096214c6e37268a5a90498d6d4d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089247"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="bbef6-102">\<module > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="bbef6-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="bbef6-103">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="bbef6-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="bbef6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bbef6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bbef6-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bbef6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="bbef6-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bbef6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="bbef6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**モジュール >**</span><span class="sxs-lookup"><span data-stu-id="bbef6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bbef6-108">構文</span><span class="sxs-lookup"><span data-stu-id="bbef6-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbef6-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bbef6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bbef6-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbef6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbef6-111">属性</span><span class="sxs-lookup"><span data-stu-id="bbef6-111">Attributes</span></span>  
  
|<span data-ttu-id="bbef6-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="bbef6-112">**Attribute**</span></span>|<span data-ttu-id="bbef6-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="bbef6-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="bbef6-114">プロキシを実装する完全修飾型名 (<xref:System.Type.FullName%2A> プロパティによって示されます) とアセンブリ名 (<xref:System.Reflection.Assembly.FullName%2A> プロパティによって示されます) をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="bbef6-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbef6-115">子要素</span><span class="sxs-lookup"><span data-stu-id="bbef6-115">Child Elements</span></span>  
 <span data-ttu-id="bbef6-116">なし。</span><span class="sxs-lookup"><span data-stu-id="bbef6-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bbef6-117">親要素</span><span class="sxs-lookup"><span data-stu-id="bbef6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bbef6-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="bbef6-118">**Element**</span></span>|<span data-ttu-id="bbef6-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="bbef6-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bbef6-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="bbef6-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="bbef6-121">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="bbef6-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbef6-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="bbef6-122">Remarks</span></span>  
 <span data-ttu-id="bbef6-123">`module` 要素は、<xref:System.Net.IWebProxy> インターフェイスを実装するプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="bbef6-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="bbef6-124">プロキシクラスを登録すると、`module` を使用して、サポートされているプロキシ経由で情報を要求できます。</span><span class="sxs-lookup"><span data-stu-id="bbef6-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="bbef6-125">`type` 属性の値は、モジュールのクラス名と、対応するダイナミックリンクライブラリ (DLL) の名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbef6-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bbef6-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="bbef6-126">Configuration Files</span></span>  
 <span data-ttu-id="bbef6-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbef6-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbef6-128">例</span><span class="sxs-lookup"><span data-stu-id="bbef6-128">Example</span></span>  
 <span data-ttu-id="bbef6-129">次の例では、カスタムプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="bbef6-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bbef6-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbef6-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="bbef6-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="bbef6-131">Network Settings Schema</span></span>](index.md)

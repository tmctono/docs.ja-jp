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
ms.openlocfilehash: 0d108f2350d82666e3dc24f0f6854fe64ea4755f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084116"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="56f85-102">\<module> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="56f85-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="56f85-103">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="56f85-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="56f85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="56f85-104">\<configuration></span></span>  
<span data-ttu-id="56f85-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="56f85-105">\<system.net></span></span>  
<span data-ttu-id="56f85-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="56f85-106">\<defaultProxy></span></span>  
<span data-ttu-id="56f85-107">\<module></span><span class="sxs-lookup"><span data-stu-id="56f85-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f85-108">構文</span><span class="sxs-lookup"><span data-stu-id="56f85-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56f85-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="56f85-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56f85-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="56f85-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56f85-111">属性</span><span class="sxs-lookup"><span data-stu-id="56f85-111">Attributes</span></span>  
  
|<span data-ttu-id="56f85-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="56f85-112">**Attribute**</span></span>|<span data-ttu-id="56f85-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="56f85-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="56f85-114">完全修飾型名 (によって示される、<xref:System.Type.FullName%2A>プロパティ) とアセンブリ名 (によって示される、<xref:System.Reflection.Assembly.FullName%2A>プロパティ)、プロキシを実装する、コンマで区切られました。</span><span class="sxs-lookup"><span data-stu-id="56f85-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56f85-115">子要素</span><span class="sxs-lookup"><span data-stu-id="56f85-115">Child Elements</span></span>  
 <span data-ttu-id="56f85-116">なし。</span><span class="sxs-lookup"><span data-stu-id="56f85-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56f85-117">親要素</span><span class="sxs-lookup"><span data-stu-id="56f85-117">Parent Elements</span></span>  
  
|<span data-ttu-id="56f85-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="56f85-118">**Element**</span></span>|<span data-ttu-id="56f85-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="56f85-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="56f85-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="56f85-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="56f85-121">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="56f85-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56f85-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="56f85-122">Remarks</span></span>  
 <span data-ttu-id="56f85-123">`module`要素を実装するプロキシ クラスの登録、<xref:System.Net.IWebProxy>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="56f85-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="56f85-124">プロキシ クラスを登録した後`module`サポートされているプロキシを使用して情報を要求するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="56f85-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="56f85-125">値、`type`属性がモジュールのクラス名と名前の対応するダイナミック リンク ライブラリ (DLL) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56f85-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="56f85-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="56f85-126">Configuration Files</span></span>  
 <span data-ttu-id="56f85-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="56f85-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f85-128">例</span><span class="sxs-lookup"><span data-stu-id="56f85-128">Example</span></span>  
 <span data-ttu-id="56f85-129">次の例では、カスタムのプロキシ クラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="56f85-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56f85-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="56f85-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="56f85-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="56f85-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

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
ms.openlocfilehash: 15f4d10a70dc3c6abd32869f5b7b0006a799b4bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698043"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="f87be-102">\<module> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f87be-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="f87be-103">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f87be-103">Adds a new proxy module to the application.</span></span>  
  
[<span data-ttu-id="f87be-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f87be-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f87be-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f87be-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f87be-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f87be-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="f87be-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<module >** を行います。</span><span class="sxs-lookup"><span data-stu-id="f87be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87be-108">構文</span><span class="sxs-lookup"><span data-stu-id="f87be-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f87be-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f87be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f87be-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f87be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f87be-111">属性</span><span class="sxs-lookup"><span data-stu-id="f87be-111">Attributes</span></span>  
  
|<span data-ttu-id="f87be-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="f87be-112">**Attribute**</span></span>|<span data-ttu-id="f87be-113">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="f87be-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="f87be-114">プロキシを実装する完全修飾型名 (<xref:System.Type.FullName%2A> プロパティで示されます) とアセンブリ名 (<xref:System.Reflection.Assembly.FullName%2A> プロパティによって示されます) をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="f87be-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f87be-115">子要素</span><span class="sxs-lookup"><span data-stu-id="f87be-115">Child Elements</span></span>  
 <span data-ttu-id="f87be-116">なし。</span><span class="sxs-lookup"><span data-stu-id="f87be-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f87be-117">親要素</span><span class="sxs-lookup"><span data-stu-id="f87be-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f87be-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="f87be-118">**Element**</span></span>|<span data-ttu-id="f87be-119">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="f87be-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f87be-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f87be-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f87be-121">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f87be-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f87be-122">コメント</span><span class="sxs-lookup"><span data-stu-id="f87be-122">Remarks</span></span>  
 <span data-ttu-id="f87be-123">@No__t-0 要素は、<xref:System.Net.IWebProxy> インターフェイスを実装するプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="f87be-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="f87be-124">プロキシクラスを登録した後、`module` を使用して、サポートされているプロキシ経由で情報を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f87be-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="f87be-125">@No__t-0 属性の値には、モジュールのクラス名と、対応するダイナミックリンクライブラリ (DLL) の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f87be-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f87be-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f87be-126">Configuration Files</span></span>  
 <span data-ttu-id="f87be-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f87be-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f87be-128">例</span><span class="sxs-lookup"><span data-stu-id="f87be-128">Example</span></span>  
 <span data-ttu-id="f87be-129">次の例では、カスタムプロキシクラスを登録します。</span><span class="sxs-lookup"><span data-stu-id="f87be-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f87be-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f87be-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f87be-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f87be-131">Network Settings Schema</span></span>](index.md)

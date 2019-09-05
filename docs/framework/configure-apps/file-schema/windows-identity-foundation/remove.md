---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251921"
---
# <a name="remove"></a><span data-ttu-id="df54b-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="df54b-101">\<remove></span></span>
<span data-ttu-id="df54b-102">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="df54b-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="df54b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="df54b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="df54b-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="df54b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="df54b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="df54b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="df54b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="df54b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="df54b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の削除**</span><span class="sxs-lookup"><span data-stu-id="df54b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df54b-108">構文</span><span class="sxs-lookup"><span data-stu-id="df54b-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df54b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="df54b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="df54b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="df54b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df54b-111">属性</span><span class="sxs-lookup"><span data-stu-id="df54b-111">Attributes</span></span>  
  
|<span data-ttu-id="df54b-112">属性</span><span class="sxs-lookup"><span data-stu-id="df54b-112">Attribute</span></span>|<span data-ttu-id="df54b-113">説明</span><span class="sxs-lookup"><span data-stu-id="df54b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df54b-114">種類</span><span class="sxs-lookup"><span data-stu-id="df54b-114">type</span></span>|<span data-ttu-id="df54b-115">削除するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="df54b-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="df54b-116">`type`属性を指定する方法の詳細については、「[カスタム型参照](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df54b-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="df54b-117">必須。</span><span class="sxs-lookup"><span data-stu-id="df54b-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df54b-118">子要素</span><span class="sxs-lookup"><span data-stu-id="df54b-118">Child Elements</span></span>  
 <span data-ttu-id="df54b-119">なし</span><span class="sxs-lookup"><span data-stu-id="df54b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df54b-120">親要素</span><span class="sxs-lookup"><span data-stu-id="df54b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="df54b-121">要素</span><span class="sxs-lookup"><span data-stu-id="df54b-121">Element</span></span>|<span data-ttu-id="df54b-122">説明</span><span class="sxs-lookup"><span data-stu-id="df54b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df54b-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="df54b-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="df54b-124">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="df54b-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="df54b-125">例</span><span class="sxs-lookup"><span data-stu-id="df54b-125">Example</span></span>  
 <span data-ttu-id="df54b-126">次の XML は、 `<add>`および`<remove>`要素を使用して、既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df54b-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="df54b-127">XML は、「」の`ClaimsAwareWebFarm`サンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="df54b-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

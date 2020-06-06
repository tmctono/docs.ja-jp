---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251921"
---
# \<remove>
<span data-ttu-id="27904-101">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="27904-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="27904-102">構文</span><span class="sxs-lookup"><span data-stu-id="27904-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27904-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="27904-103">Attributes and Elements</span></span>  
 <span data-ttu-id="27904-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="27904-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27904-105">属性</span><span class="sxs-lookup"><span data-stu-id="27904-105">Attributes</span></span>  
  
|<span data-ttu-id="27904-106">属性</span><span class="sxs-lookup"><span data-stu-id="27904-106">Attribute</span></span>|<span data-ttu-id="27904-107">説明</span><span class="sxs-lookup"><span data-stu-id="27904-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27904-108">type</span><span class="sxs-lookup"><span data-stu-id="27904-108">type</span></span>|<span data-ttu-id="27904-109">削除するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="27904-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="27904-110">属性を指定する方法の詳細については `type` 、「[カスタム型参照](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27904-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="27904-111">必須。</span><span class="sxs-lookup"><span data-stu-id="27904-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27904-112">子要素</span><span class="sxs-lookup"><span data-stu-id="27904-112">Child Elements</span></span>  
 <span data-ttu-id="27904-113">なし</span><span class="sxs-lookup"><span data-stu-id="27904-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27904-114">親要素</span><span class="sxs-lookup"><span data-stu-id="27904-114">Parent Elements</span></span>  
  
|<span data-ttu-id="27904-115">要素</span><span class="sxs-lookup"><span data-stu-id="27904-115">Element</span></span>|<span data-ttu-id="27904-116">Description</span><span class="sxs-lookup"><span data-stu-id="27904-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="27904-117">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="27904-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27904-118">例</span><span class="sxs-lookup"><span data-stu-id="27904-118">Example</span></span>  
 <span data-ttu-id="27904-119">次の XML は、および要素を使用して、 `<add>` `<remove>` 既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="27904-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="27904-120">XML は、「」のサンプルから抜粋したものです `ClaimsAwareWebFarm` 。</span><span class="sxs-lookup"><span data-stu-id="27904-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

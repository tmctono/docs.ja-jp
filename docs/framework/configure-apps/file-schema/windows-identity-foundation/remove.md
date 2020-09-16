---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 7581f581c4b97a07eb4bdeb49eb5ae5ce72c2aa7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535717"
---
# \<remove>
<span data-ttu-id="d13e4-101">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="d13e4-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="d13e4-102">構文</span><span class="sxs-lookup"><span data-stu-id="d13e4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d13e4-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d13e4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d13e4-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d13e4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d13e4-105">属性</span><span class="sxs-lookup"><span data-stu-id="d13e4-105">Attributes</span></span>  
  
|<span data-ttu-id="d13e4-106">属性</span><span class="sxs-lookup"><span data-stu-id="d13e4-106">Attribute</span></span>|<span data-ttu-id="d13e4-107">説明</span><span class="sxs-lookup"><span data-stu-id="d13e4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d13e4-108">type</span><span class="sxs-lookup"><span data-stu-id="d13e4-108">type</span></span>|<span data-ttu-id="d13e4-109">削除するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="d13e4-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="d13e4-110">属性を指定する方法の詳細については `type` 、「 [カスタム型参照](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d13e4-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="d13e4-111">必須です。</span><span class="sxs-lookup"><span data-stu-id="d13e4-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d13e4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d13e4-112">Child Elements</span></span>  
 <span data-ttu-id="d13e4-113">なし</span><span class="sxs-lookup"><span data-stu-id="d13e4-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d13e4-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d13e4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d13e4-115">要素</span><span class="sxs-lookup"><span data-stu-id="d13e4-115">Element</span></span>|<span data-ttu-id="d13e4-116">説明</span><span class="sxs-lookup"><span data-stu-id="d13e4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="d13e4-117">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d13e4-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d13e4-118">例</span><span class="sxs-lookup"><span data-stu-id="d13e4-118">Example</span></span>  
 <span data-ttu-id="d13e4-119">次の XML は、および要素を使用して、 `<add>` `<remove>` 既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d13e4-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="d13e4-120">XML は、「」のサンプルから抜粋したものです `ClaimsAwareWebFarm` 。</span><span class="sxs-lookup"><span data-stu-id="d13e4-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

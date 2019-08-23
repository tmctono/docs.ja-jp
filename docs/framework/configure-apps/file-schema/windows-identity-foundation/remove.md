---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942583"
---
# <a name="remove"></a><span data-ttu-id="7f78f-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="7f78f-101">\<remove></span></span>
<span data-ttu-id="7f78f-102">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="7f78f-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="7f78f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7f78f-103">\<system.identityModel></span></span>  
<span data-ttu-id="7f78f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7f78f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7f78f-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7f78f-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7f78f-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="7f78f-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f78f-107">構文</span><span class="sxs-lookup"><span data-stu-id="7f78f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f78f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f78f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7f78f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f78f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f78f-110">属性</span><span class="sxs-lookup"><span data-stu-id="7f78f-110">Attributes</span></span>  
  
|<span data-ttu-id="7f78f-111">属性</span><span class="sxs-lookup"><span data-stu-id="7f78f-111">Attribute</span></span>|<span data-ttu-id="7f78f-112">説明</span><span class="sxs-lookup"><span data-stu-id="7f78f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f78f-113">型</span><span class="sxs-lookup"><span data-stu-id="7f78f-113">type</span></span>|<span data-ttu-id="7f78f-114">削除するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="7f78f-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="7f78f-115">`type`属性を指定する方法の詳細については、「[カスタム型参照](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f78f-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="7f78f-116">必須。</span><span class="sxs-lookup"><span data-stu-id="7f78f-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f78f-117">子要素</span><span class="sxs-lookup"><span data-stu-id="7f78f-117">Child Elements</span></span>  
 <span data-ttu-id="7f78f-118">なし</span><span class="sxs-lookup"><span data-stu-id="7f78f-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f78f-119">親要素</span><span class="sxs-lookup"><span data-stu-id="7f78f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7f78f-120">要素</span><span class="sxs-lookup"><span data-stu-id="7f78f-120">Element</span></span>|<span data-ttu-id="7f78f-121">説明</span><span class="sxs-lookup"><span data-stu-id="7f78f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f78f-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7f78f-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="7f78f-123">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f78f-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f78f-124">例</span><span class="sxs-lookup"><span data-stu-id="7f78f-124">Example</span></span>  
 <span data-ttu-id="7f78f-125">次の XML は、 `<add>`および`<remove>`要素を使用して、既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f78f-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="7f78f-126">XML は、「」の`ClaimsAwareWebFarm`サンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="7f78f-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

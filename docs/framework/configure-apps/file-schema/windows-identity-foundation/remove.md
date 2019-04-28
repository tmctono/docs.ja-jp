---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793888"
---
# <a name="remove"></a><span data-ttu-id="999fd-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="999fd-101">\<remove></span></span>
<span data-ttu-id="999fd-102">トークン ハンドラー コレクションから指定したセキュリティ トークン ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="999fd-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="999fd-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="999fd-103">\<system.identityModel></span></span>  
<span data-ttu-id="999fd-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="999fd-104">\<identityConfiguration></span></span>  
<span data-ttu-id="999fd-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="999fd-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="999fd-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="999fd-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999fd-107">構文</span><span class="sxs-lookup"><span data-stu-id="999fd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="999fd-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="999fd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="999fd-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="999fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="999fd-110">属性</span><span class="sxs-lookup"><span data-stu-id="999fd-110">Attributes</span></span>  
  
|<span data-ttu-id="999fd-111">属性</span><span class="sxs-lookup"><span data-stu-id="999fd-111">Attribute</span></span>|<span data-ttu-id="999fd-112">説明</span><span class="sxs-lookup"><span data-stu-id="999fd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="999fd-113">種類</span><span class="sxs-lookup"><span data-stu-id="999fd-113">type</span></span>|<span data-ttu-id="999fd-114">削除するトークン ハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="999fd-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="999fd-115">詳細を指定する方法については、`type`属性は、「[カスタム型の参照](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)します。</span><span class="sxs-lookup"><span data-stu-id="999fd-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="999fd-116">必須。</span><span class="sxs-lookup"><span data-stu-id="999fd-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="999fd-117">子要素</span><span class="sxs-lookup"><span data-stu-id="999fd-117">Child Elements</span></span>  
 <span data-ttu-id="999fd-118">なし</span><span class="sxs-lookup"><span data-stu-id="999fd-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="999fd-119">親要素</span><span class="sxs-lookup"><span data-stu-id="999fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="999fd-120">要素</span><span class="sxs-lookup"><span data-stu-id="999fd-120">Element</span></span>|<span data-ttu-id="999fd-121">説明</span><span class="sxs-lookup"><span data-stu-id="999fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="999fd-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="999fd-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="999fd-123">エンドポイントに登録されているセキュリティ トークン ハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="999fd-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="999fd-124">例</span><span class="sxs-lookup"><span data-stu-id="999fd-124">Example</span></span>  
 <span data-ttu-id="999fd-125">次の XML の使用を示しています、`<add>`と`<remove>`に既定のセッション トークン ハンドラーをカスタム セッション トークン ハンドラーに置き換える要素。</span><span class="sxs-lookup"><span data-stu-id="999fd-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="999fd-126">XML から取得されますが、`ClaimsAwareWebFarm`サンプル。</span><span class="sxs-lookup"><span data-stu-id="999fd-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

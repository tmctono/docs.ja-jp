---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 3ea9684245bd1c1c3b9ce171a045fff49d0ba592
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156915"
---
# \<serviceTokenResolver>

<span data-ttu-id="c17b7-101">トークンハンドラーコレクションのハンドラーによって使用されるサービストークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="c17b7-101">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c17b7-102">サービストークンリゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-102">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="c17b7-103">構文</span><span class="sxs-lookup"><span data-stu-id="c17b7-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c17b7-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c17b7-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c17b7-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c17b7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c17b7-106">属性</span><span class="sxs-lookup"><span data-stu-id="c17b7-106">Attributes</span></span>  
  
|<span data-ttu-id="c17b7-107">属性</span><span class="sxs-lookup"><span data-stu-id="c17b7-107">Attribute</span></span>|<span data-ttu-id="c17b7-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="c17b7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c17b7-109">type</span><span class="sxs-lookup"><span data-stu-id="c17b7-109">type</span></span>|<span data-ttu-id="c17b7-110">サービストークンリゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c17b7-110">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="c17b7-111"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラスから派生した型または型 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 。</span><span class="sxs-lookup"><span data-stu-id="c17b7-111">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="c17b7-112">属性を指定する方法の詳細については `type` 、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c17b7-112">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="c17b7-113">必須。</span><span class="sxs-lookup"><span data-stu-id="c17b7-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c17b7-114">子要素</span><span class="sxs-lookup"><span data-stu-id="c17b7-114">Child Elements</span></span>  

 <span data-ttu-id="c17b7-115">None</span><span class="sxs-lookup"><span data-stu-id="c17b7-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c17b7-116">親要素</span><span class="sxs-lookup"><span data-stu-id="c17b7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c17b7-117">要素</span><span class="sxs-lookup"><span data-stu-id="c17b7-117">Element</span></span>|<span data-ttu-id="c17b7-118">説明</span><span class="sxs-lookup"><span data-stu-id="c17b7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="c17b7-119">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="c17b7-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c17b7-120">解説</span><span class="sxs-lookup"><span data-stu-id="c17b7-120">Remarks</span></span>  

 <span data-ttu-id="c17b7-121">サービストークンリゾルバーを使用して、受信トークンとメッセージの暗号化トークンを解決できます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-121">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="c17b7-122">これは、受信トークンの暗号化を解除するために使用する必要があるキーを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-122">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="c17b7-123">属性を指定する必要があり `type` ます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-123">You must specify the `type` attribute.</span></span> <span data-ttu-id="c17b7-124">指定できる型は、 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> またはクラスから派生したカスタム型のいずれか <xref:System.IdentityModel.Selectors.SecurityTokenResolver> です。</span><span class="sxs-lookup"><span data-stu-id="c17b7-124">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="c17b7-125">一部のトークンハンドラーでは、構成でサービストークンリゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-125">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="c17b7-126">個々のトークンハンドラーの設定は、セキュリティトークンハンドラーコレクションで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-126">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c17b7-127">要素 `<serviceTokenResolver>` の子要素としての指定 [\<identityConfiguration>](identityconfiguration.md) は非推奨とされましたが、旧バージョンとの互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c17b7-127">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="c17b7-128">要素の設定は、要素の設定 `<securityTokenHandlerConfiguration>` よりも優先さ `<identityConfiguration>` れます。</span><span class="sxs-lookup"><span data-stu-id="c17b7-128">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c17b7-129">例</span><span class="sxs-lookup"><span data-stu-id="c17b7-129">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```

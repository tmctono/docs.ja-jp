---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152750"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="da0f6-101">\<クレーム認証マネージャー></span><span class="sxs-lookup"><span data-stu-id="da0f6-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="da0f6-102">受信要求のクレーム認証マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="da0f6-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da0f6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da0f6-104">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="da0f6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="da0f6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="da0f6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="da0f6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<クレーム認証マネージャー>**</span><span class="sxs-lookup"><span data-stu-id="da0f6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da0f6-107">構文</span><span class="sxs-lookup"><span data-stu-id="da0f6-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da0f6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="da0f6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="da0f6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da0f6-110">属性</span><span class="sxs-lookup"><span data-stu-id="da0f6-110">Attributes</span></span>  
  
|<span data-ttu-id="da0f6-111">属性</span><span class="sxs-lookup"><span data-stu-id="da0f6-111">Attribute</span></span>|<span data-ttu-id="da0f6-112">説明</span><span class="sxs-lookup"><span data-stu-id="da0f6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da0f6-113">type</span><span class="sxs-lookup"><span data-stu-id="da0f6-113">type</span></span>|<span data-ttu-id="da0f6-114">クラスから派生するカスタム型を指定します<xref:System.Security.Claims.ClaimsAuthenticationManager>。</span><span class="sxs-lookup"><span data-stu-id="da0f6-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="da0f6-115">`type`属性の指定方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da0f6-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da0f6-116">子要素</span><span class="sxs-lookup"><span data-stu-id="da0f6-116">Child Elements</span></span>  
 <span data-ttu-id="da0f6-117">属性がない`type`場合、または属性がクラスを`type`参照している<xref:System.Security.Claims.ClaimsAuthenticationManager>場合、`<claimsAuthenticationManager>`要素は子要素を受け取りません。ただし、派生したクラス<xref:System.Security.Claims.ClaimsAuthenticationManager>は子構成要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da0f6-118">親要素</span><span class="sxs-lookup"><span data-stu-id="da0f6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="da0f6-119">要素</span><span class="sxs-lookup"><span data-stu-id="da0f6-119">Element</span></span>|<span data-ttu-id="da0f6-120">説明</span><span class="sxs-lookup"><span data-stu-id="da0f6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da0f6-121">\<id構成></span><span class="sxs-lookup"><span data-stu-id="da0f6-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="da0f6-122">サービス レベルの ID 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da0f6-123">解説</span><span class="sxs-lookup"><span data-stu-id="da0f6-123">Remarks</span></span>  
 <span data-ttu-id="da0f6-124">クラスを通じて指定される<xref:System.Security.Claims.ClaimsAuthenticationManager>既定の動作は、受信した要求をエコーします。</span><span class="sxs-lookup"><span data-stu-id="da0f6-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="da0f6-125">属性が`type`指定されていない場合、または属性`type`がクラスを<xref:System.Security.Claims.ClaimsAuthenticationManager>指定する場合`<claimsAuthenticationManager>`、要素は子要素を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="da0f6-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="da0f6-126">クラスから派生した`type`型を登録してカスタム動作を実装<xref:System.Security.Claims.ClaimsAuthenticationManager>する属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="da0f6-127">派生クラスは、これらの要素を処理するメソッド`<claimsAuthenticationManager>`をオーバーライドすることで、要素<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>の子要素を通じて構成をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="da0f6-128">子要素に対して定義されたスキーマは、クラスのデザイナーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="da0f6-129">要素`<claimsAuthenticationManager>`は、プロパティ<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>を設定します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da0f6-130">例</span><span class="sxs-lookup"><span data-stu-id="da0f6-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

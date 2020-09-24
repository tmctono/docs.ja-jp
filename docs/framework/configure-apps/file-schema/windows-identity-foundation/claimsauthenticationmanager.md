---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 9e099b8de486631702548b8a035a46a7e0f4eb30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158475"
---
# \<claimsAuthenticationManager>

<span data-ttu-id="57ec9-101">入力方向の要求に対して要求認証マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="57ec9-101">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="57ec9-102">構文</span><span class="sxs-lookup"><span data-stu-id="57ec9-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57ec9-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="57ec9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="57ec9-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="57ec9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57ec9-105">属性</span><span class="sxs-lookup"><span data-stu-id="57ec9-105">Attributes</span></span>  
  
|<span data-ttu-id="57ec9-106">属性</span><span class="sxs-lookup"><span data-stu-id="57ec9-106">Attribute</span></span>|<span data-ttu-id="57ec9-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="57ec9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57ec9-108">type</span><span class="sxs-lookup"><span data-stu-id="57ec9-108">type</span></span>|<span data-ttu-id="57ec9-109">クラスから派生するカスタム型を指定し <xref:System.Security.Claims.ClaimsAuthenticationManager> ます。</span><span class="sxs-lookup"><span data-stu-id="57ec9-109">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="57ec9-110">属性を指定する方法の詳細については `type` 、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57ec9-110">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57ec9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="57ec9-111">Child Elements</span></span>  

 <span data-ttu-id="57ec9-112">属性が存在しない場合、 `type` または属性がクラスを参照している場合、 `type` 要素は <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 子要素を受け取りません。ただし、から派生したクラス <xref:System.Security.Claims.ClaimsAuthenticationManager> は子構成要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="57ec9-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57ec9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="57ec9-113">Parent Elements</span></span>  
  
|<span data-ttu-id="57ec9-114">要素</span><span class="sxs-lookup"><span data-stu-id="57ec9-114">Element</span></span>|<span data-ttu-id="57ec9-115">説明</span><span class="sxs-lookup"><span data-stu-id="57ec9-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="57ec9-116">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="57ec9-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57ec9-117">解説</span><span class="sxs-lookup"><span data-stu-id="57ec9-117">Remarks</span></span>  

 <span data-ttu-id="57ec9-118">クラスによって提供される既定の動作では、 <xref:System.Security.Claims.ClaimsAuthenticationManager> 入力方向の要求がエコーされます。</span><span class="sxs-lookup"><span data-stu-id="57ec9-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="57ec9-119">属性が指定されていない場合、 `type` または属性でクラスが指定されている場合、 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> 要素は `<claimsAuthenticationManager>` 子要素を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="57ec9-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="57ec9-120">属性を指定して、 `type` クラスから派生した型を登録し、 <xref:System.Security.Claims.ClaimsAuthenticationManager> カスタム動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="57ec9-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="57ec9-121">派生クラスでは、要素の子要素を使用した構成をサポートできます。これを行う `<claimsAuthenticationManager>` には、メソッドをオーバーライドして <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> これらの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="57ec9-121">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="57ec9-122">子要素に対して定義されているスキーマは、クラスのデザイナーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="57ec9-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="57ec9-123">要素は、 `<claimsAuthenticationManager>` プロパティを設定し <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="57ec9-123">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57ec9-124">例</span><span class="sxs-lookup"><span data-stu-id="57ec9-124">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

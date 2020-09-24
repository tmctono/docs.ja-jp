---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 1b5427210142c70c31c5f736c9b5e281dca53f33
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150870"
---
# \<claimType>

<span data-ttu-id="c6d62-101">入力方向のセキュリティトークンに対して1つの省略可能なクレームまたは必須の要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="c6d62-102">構文</span><span class="sxs-lookup"><span data-stu-id="c6d62-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6d62-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c6d62-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c6d62-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6d62-105">属性</span><span class="sxs-lookup"><span data-stu-id="c6d62-105">Attributes</span></span>  
  
|<span data-ttu-id="c6d62-106">属性</span><span class="sxs-lookup"><span data-stu-id="c6d62-106">Attribute</span></span>|<span data-ttu-id="c6d62-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="c6d62-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6d62-108">type</span><span class="sxs-lookup"><span data-stu-id="c6d62-108">type</span></span>|<span data-ttu-id="c6d62-109">クレームの種類。</span><span class="sxs-lookup"><span data-stu-id="c6d62-109">The claim type.</span></span> <span data-ttu-id="c6d62-110">通常は URI です。</span><span class="sxs-lookup"><span data-stu-id="c6d62-110">Typically a URI.</span></span> <span data-ttu-id="c6d62-111">必須。</span><span class="sxs-lookup"><span data-stu-id="c6d62-111">Required.</span></span>|  
|<span data-ttu-id="c6d62-112">オプション</span><span class="sxs-lookup"><span data-stu-id="c6d62-112">optional</span></span>|<span data-ttu-id="c6d62-113">要求の種類が省略可能かどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="c6d62-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="c6d62-114">省略可能。</span><span class="sxs-lookup"><span data-stu-id="c6d62-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6d62-115">子要素</span><span class="sxs-lookup"><span data-stu-id="c6d62-115">Child Elements</span></span>  

 <span data-ttu-id="c6d62-116">None</span><span class="sxs-lookup"><span data-stu-id="c6d62-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6d62-117">親要素</span><span class="sxs-lookup"><span data-stu-id="c6d62-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c6d62-118">要素</span><span class="sxs-lookup"><span data-stu-id="c6d62-118">Element</span></span>|<span data-ttu-id="c6d62-119">説明</span><span class="sxs-lookup"><span data-stu-id="c6d62-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="c6d62-120">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-120">Specifies the set of required claims for incoming security tokens.</span></span>|

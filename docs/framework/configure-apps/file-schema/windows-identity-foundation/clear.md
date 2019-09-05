---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252041"
---
# <a name="clear"></a><span data-ttu-id="d92be-101">\<clear></span><span class="sxs-lookup"><span data-stu-id="d92be-101">\<clear></span></span>
<span data-ttu-id="d92be-102">現在のトークンハンドラーコレクションからすべてのセキュリティトークンハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d92be-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="d92be-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d92be-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d92be-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d92be-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d92be-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d92be-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d92be-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d92be-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d92be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="d92be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92be-108">構文</span><span class="sxs-lookup"><span data-stu-id="d92be-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d92be-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d92be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d92be-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d92be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d92be-111">属性</span><span class="sxs-lookup"><span data-stu-id="d92be-111">Attributes</span></span>  
 <span data-ttu-id="d92be-112">なし</span><span class="sxs-lookup"><span data-stu-id="d92be-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d92be-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d92be-113">Child Elements</span></span>  
 <span data-ttu-id="d92be-114">なし</span><span class="sxs-lookup"><span data-stu-id="d92be-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d92be-115">親要素</span><span class="sxs-lookup"><span data-stu-id="d92be-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d92be-116">要素</span><span class="sxs-lookup"><span data-stu-id="d92be-116">Element</span></span>|<span data-ttu-id="d92be-117">説明</span><span class="sxs-lookup"><span data-stu-id="d92be-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d92be-118">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d92be-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="d92be-119">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d92be-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|

---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: 0f043442fb8edd9bf95a839a26cc42e8122d9100
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167068"
---
# \<clear>

<span data-ttu-id="d0504-101">現在のトークンハンドラーコレクションからすべてのセキュリティトークンハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d0504-101">Clears all security token handlers from the current token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="d0504-102">構文</span><span class="sxs-lookup"><span data-stu-id="d0504-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0504-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d0504-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d0504-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0504-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0504-105">属性</span><span class="sxs-lookup"><span data-stu-id="d0504-105">Attributes</span></span>  

 <span data-ttu-id="d0504-106">None</span><span class="sxs-lookup"><span data-stu-id="d0504-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0504-107">子要素</span><span class="sxs-lookup"><span data-stu-id="d0504-107">Child Elements</span></span>  

 <span data-ttu-id="d0504-108">None</span><span class="sxs-lookup"><span data-stu-id="d0504-108">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0504-109">親要素</span><span class="sxs-lookup"><span data-stu-id="d0504-109">Parent Elements</span></span>  
  
|<span data-ttu-id="d0504-110">要素</span><span class="sxs-lookup"><span data-stu-id="d0504-110">Element</span></span>|<span data-ttu-id="d0504-111">説明</span><span class="sxs-lookup"><span data-stu-id="d0504-111">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="d0504-112">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0504-112">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|

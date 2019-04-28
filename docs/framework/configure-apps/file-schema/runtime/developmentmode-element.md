---
title: <developmentMode> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf840035150f08c894c984213af9a0abe6e95af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704766"
---
# <a name="developmentmode-element"></a><span data-ttu-id="52e2b-102">\<developmentMode > 要素</span><span class="sxs-lookup"><span data-stu-id="52e2b-102">\<developmentMode> Element</span></span>
<span data-ttu-id="52e2b-103">DEVPATH 環境変数によって指定されたディレクトリで、ランタイムがアセンブリの検索を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="52e2b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="52e2b-104">\<configuration></span></span>  
<span data-ttu-id="52e2b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="52e2b-105">\<runtime></span></span>  
<span data-ttu-id="52e2b-106">\<developmentMode></span><span class="sxs-lookup"><span data-stu-id="52e2b-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e2b-107">構文</span><span class="sxs-lookup"><span data-stu-id="52e2b-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52e2b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="52e2b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="52e2b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52e2b-110">属性</span><span class="sxs-lookup"><span data-stu-id="52e2b-110">Attributes</span></span>  
  
|<span data-ttu-id="52e2b-111">属性</span><span class="sxs-lookup"><span data-stu-id="52e2b-111">Attribute</span></span>|<span data-ttu-id="52e2b-112">説明</span><span class="sxs-lookup"><span data-stu-id="52e2b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52e2b-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="52e2b-113">**developerInstallation**</span></span>|<span data-ttu-id="52e2b-114">DEVPATH 環境変数によって指定されたディレクトリで、ランタイムがアセンブリの検索を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="52e2b-115">developerInstallation 属性</span><span class="sxs-lookup"><span data-stu-id="52e2b-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="52e2b-116">[値]</span><span class="sxs-lookup"><span data-stu-id="52e2b-116">Value</span></span>|<span data-ttu-id="52e2b-117">説明</span><span class="sxs-lookup"><span data-stu-id="52e2b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52e2b-118">**true**</span><span class="sxs-lookup"><span data-stu-id="52e2b-118">**true**</span></span>|<span data-ttu-id="52e2b-119">DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="52e2b-120">**false**</span><span class="sxs-lookup"><span data-stu-id="52e2b-120">**false**</span></span>|<span data-ttu-id="52e2b-121">DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリを検索しません。</span><span class="sxs-lookup"><span data-stu-id="52e2b-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="52e2b-122">これは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="52e2b-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52e2b-123">子要素</span><span class="sxs-lookup"><span data-stu-id="52e2b-123">Child Elements</span></span>  
 <span data-ttu-id="52e2b-124">なし。</span><span class="sxs-lookup"><span data-stu-id="52e2b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52e2b-125">親要素</span><span class="sxs-lookup"><span data-stu-id="52e2b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="52e2b-126">要素</span><span class="sxs-lookup"><span data-stu-id="52e2b-126">Element</span></span>|<span data-ttu-id="52e2b-127">説明</span><span class="sxs-lookup"><span data-stu-id="52e2b-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="52e2b-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="52e2b-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="52e2b-129">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="52e2b-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52e2b-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="52e2b-130">Remarks</span></span>  
 <span data-ttu-id="52e2b-131">開発時にのみ、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-131">Use this setting only at development time.</span></span> <span data-ttu-id="52e2b-132">ランタイムは、DEVPATH に厳密な名前のアセンブリのバージョンをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="52e2b-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="52e2b-133">単に最初に見つかったアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52e2b-134">例</span><span class="sxs-lookup"><span data-stu-id="52e2b-134">Example</span></span>  
 <span data-ttu-id="52e2b-135">次の例では、ランタイムが DEVPATH 環境変数で指定されたディレクトリでアセンブリを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="52e2b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="52e2b-136">See also</span></span>

- [<span data-ttu-id="52e2b-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="52e2b-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="52e2b-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="52e2b-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="52e2b-139">方法: DEVPATH を使用してアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="52e2b-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)

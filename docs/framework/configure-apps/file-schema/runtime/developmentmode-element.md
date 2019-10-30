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
ms.openlocfilehash: 4a062da31740edb8f0c7a4f4db8b09800c687587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117633"
---
# <a name="developmentmode-element"></a><span data-ttu-id="be8f5-102">\<developmentMode > 要素</span><span class="sxs-lookup"><span data-stu-id="be8f5-102">\<developmentMode> Element</span></span>
<span data-ttu-id="be8f5-103">DEVPATH 環境変数によって指定されたディレクトリで、ランタイムがアセンブリの検索を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="be8f5-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="be8f5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="be8f5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="be8f5-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="be8f5-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="be8f5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode >**</span><span class="sxs-lookup"><span data-stu-id="be8f5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be8f5-107">構文</span><span class="sxs-lookup"><span data-stu-id="be8f5-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be8f5-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="be8f5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="be8f5-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="be8f5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be8f5-110">属性</span><span class="sxs-lookup"><span data-stu-id="be8f5-110">Attributes</span></span>  
  
|<span data-ttu-id="be8f5-111">属性</span><span class="sxs-lookup"><span data-stu-id="be8f5-111">Attribute</span></span>|<span data-ttu-id="be8f5-112">説明</span><span class="sxs-lookup"><span data-stu-id="be8f5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be8f5-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="be8f5-113">**developerInstallation**</span></span>|<span data-ttu-id="be8f5-114">DEVPATH 環境変数によって指定されたディレクトリで、ランタイムがアセンブリの検索を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="be8f5-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="be8f5-115">developerInstallation 属性</span><span class="sxs-lookup"><span data-stu-id="be8f5-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="be8f5-116">[値]</span><span class="sxs-lookup"><span data-stu-id="be8f5-116">Value</span></span>|<span data-ttu-id="be8f5-117">説明</span><span class="sxs-lookup"><span data-stu-id="be8f5-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="be8f5-118">**true**</span><span class="sxs-lookup"><span data-stu-id="be8f5-118">**true**</span></span>|<span data-ttu-id="be8f5-119">DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="be8f5-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="be8f5-120">**false**</span><span class="sxs-lookup"><span data-stu-id="be8f5-120">**false**</span></span>|<span data-ttu-id="be8f5-121">は、DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリを検索しません。</span><span class="sxs-lookup"><span data-stu-id="be8f5-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="be8f5-122">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="be8f5-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be8f5-123">子要素</span><span class="sxs-lookup"><span data-stu-id="be8f5-123">Child Elements</span></span>  
 <span data-ttu-id="be8f5-124">なし。</span><span class="sxs-lookup"><span data-stu-id="be8f5-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be8f5-125">親要素</span><span class="sxs-lookup"><span data-stu-id="be8f5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="be8f5-126">要素</span><span class="sxs-lookup"><span data-stu-id="be8f5-126">Element</span></span>|<span data-ttu-id="be8f5-127">説明</span><span class="sxs-lookup"><span data-stu-id="be8f5-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="be8f5-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="be8f5-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="be8f5-129">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be8f5-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be8f5-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="be8f5-130">Remarks</span></span>  
 <span data-ttu-id="be8f5-131">この設定は、開発時にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="be8f5-131">Use this setting only at development time.</span></span> <span data-ttu-id="be8f5-132">ランタイムは、DEVPATH で見つかった厳密な名前のアセンブリのバージョンをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="be8f5-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="be8f5-133">単純に、最初に見つかったアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="be8f5-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be8f5-134">例</span><span class="sxs-lookup"><span data-stu-id="be8f5-134">Example</span></span>  
 <span data-ttu-id="be8f5-135">次の例は、DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリをランタイムが検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="be8f5-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be8f5-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="be8f5-136">See also</span></span>

- [<span data-ttu-id="be8f5-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="be8f5-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="be8f5-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="be8f5-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="be8f5-139">方法 : DEVPATH を使用してアセンブリを指定する</span><span class="sxs-lookup"><span data-stu-id="be8f5-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)

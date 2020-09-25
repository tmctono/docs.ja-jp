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
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205023"
---
# <a name="developmentmode-element"></a><span data-ttu-id="06823-102">\<developmentMode> 要素</span><span class="sxs-lookup"><span data-stu-id="06823-102">\<developmentMode> Element</span></span>

<span data-ttu-id="06823-103">DEVPATH 環境変数によって指定されたディレクトリで、ランタイムがアセンブリの検索を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="06823-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="06823-104">構文</span><span class="sxs-lookup"><span data-stu-id="06823-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06823-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06823-105">Attributes and Elements</span></span>  

 <span data-ttu-id="06823-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="06823-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06823-107">属性</span><span class="sxs-lookup"><span data-stu-id="06823-107">Attributes</span></span>  
  
|<span data-ttu-id="06823-108">属性</span><span class="sxs-lookup"><span data-stu-id="06823-108">Attribute</span></span>|<span data-ttu-id="06823-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="06823-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06823-110">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="06823-110">**developerInstallation**</span></span>|<span data-ttu-id="06823-111">DEVPATH 環境変数によって指定されたディレクトリで、ランタイムがアセンブリの検索を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="06823-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="06823-112">developerInstallation 属性</span><span class="sxs-lookup"><span data-stu-id="06823-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="06823-113">値</span><span class="sxs-lookup"><span data-stu-id="06823-113">Value</span></span>|<span data-ttu-id="06823-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="06823-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="06823-115">**true**</span><span class="sxs-lookup"><span data-stu-id="06823-115">**true**</span></span>|<span data-ttu-id="06823-116">DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="06823-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="06823-117">**false**</span><span class="sxs-lookup"><span data-stu-id="06823-117">**false**</span></span>|<span data-ttu-id="06823-118">は、DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリを検索しません。</span><span class="sxs-lookup"><span data-stu-id="06823-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="06823-119">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="06823-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06823-120">子要素</span><span class="sxs-lookup"><span data-stu-id="06823-120">Child Elements</span></span>  

 <span data-ttu-id="06823-121">なし。</span><span class="sxs-lookup"><span data-stu-id="06823-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06823-122">親要素</span><span class="sxs-lookup"><span data-stu-id="06823-122">Parent Elements</span></span>  
  
|<span data-ttu-id="06823-123">要素</span><span class="sxs-lookup"><span data-stu-id="06823-123">Element</span></span>|<span data-ttu-id="06823-124">説明</span><span class="sxs-lookup"><span data-stu-id="06823-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06823-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="06823-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="06823-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06823-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06823-127">解説</span><span class="sxs-lookup"><span data-stu-id="06823-127">Remarks</span></span>  

 <span data-ttu-id="06823-128">この設定は、開発時にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="06823-128">Use this setting only at development time.</span></span> <span data-ttu-id="06823-129">ランタイムは、DEVPATH で見つかった厳密な名前のアセンブリのバージョンをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="06823-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="06823-130">単純に、最初に見つかったアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="06823-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06823-131">例</span><span class="sxs-lookup"><span data-stu-id="06823-131">Example</span></span>  

 <span data-ttu-id="06823-132">次の例は、DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリをランタイムが検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="06823-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06823-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="06823-133">See also</span></span>

- [<span data-ttu-id="06823-134">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="06823-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="06823-135">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="06823-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="06823-136">方法: DEVPATH を使用してアセンブリを指定する</span><span class="sxs-lookup"><span data-stu-id="06823-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)

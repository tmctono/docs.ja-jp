---
title: <disableCommitThreadStack> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08ffd6ffcb9a8fa356d486f6d2ae1113de0fa682
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106516"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="4137a-102">\<disableCommitThreadStack > 要素</span><span class="sxs-lookup"><span data-stu-id="4137a-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="4137a-103">スレッドの起動時にスレッド スタック全体をコミットするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4137a-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="4137a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4137a-104">\<configuration></span></span>  
<span data-ttu-id="4137a-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="4137a-105">\<runtime></span></span>  
<span data-ttu-id="4137a-106">\<disableCommitThreadStack></span><span class="sxs-lookup"><span data-stu-id="4137a-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4137a-107">構文</span><span class="sxs-lookup"><span data-stu-id="4137a-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4137a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4137a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4137a-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4137a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4137a-110">属性</span><span class="sxs-lookup"><span data-stu-id="4137a-110">Attributes</span></span>  
  
|<span data-ttu-id="4137a-111">属性</span><span class="sxs-lookup"><span data-stu-id="4137a-111">Attribute</span></span>|<span data-ttu-id="4137a-112">説明</span><span class="sxs-lookup"><span data-stu-id="4137a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4137a-113">enabled</span><span class="sxs-lookup"><span data-stu-id="4137a-113">enabled</span></span>|<span data-ttu-id="4137a-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4137a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4137a-115">スレッド起動時にスレッド スタック全体をコミットすること (既定の動作) を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4137a-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4137a-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="4137a-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4137a-117">値</span><span class="sxs-lookup"><span data-stu-id="4137a-117">Value</span></span>|<span data-ttu-id="4137a-118">説明</span><span class="sxs-lookup"><span data-stu-id="4137a-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4137a-119">0</span><span class="sxs-lookup"><span data-stu-id="4137a-119">0</span></span>|<span data-ttu-id="4137a-120">共通言語ランタイムの既定の動作 (スレッドの起動時にスレッド スタック全体をコミット) を無効にしません。</span><span class="sxs-lookup"><span data-stu-id="4137a-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="4137a-121">1</span><span class="sxs-lookup"><span data-stu-id="4137a-121">1</span></span>|<span data-ttu-id="4137a-122">共通言語ランタイムの既定の動作 (スレッドの起動時にスレッド スタック全体をコミット) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4137a-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4137a-123">子要素</span><span class="sxs-lookup"><span data-stu-id="4137a-123">Child Elements</span></span>  
 <span data-ttu-id="4137a-124">なし。</span><span class="sxs-lookup"><span data-stu-id="4137a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4137a-125">親要素</span><span class="sxs-lookup"><span data-stu-id="4137a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4137a-126">要素</span><span class="sxs-lookup"><span data-stu-id="4137a-126">Element</span></span>|<span data-ttu-id="4137a-127">説明</span><span class="sxs-lookup"><span data-stu-id="4137a-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4137a-128">共通言語ランタイムおよび [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4137a-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="4137a-129">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4137a-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4137a-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="4137a-130">Remarks</span></span>  
 <span data-ttu-id="4137a-131">共通言語ランタイムの既定の動作では、スレッドの起動時にスレッド スタック全体がコミットされます。</span><span class="sxs-lookup"><span data-stu-id="4137a-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="4137a-132">メモリが限られているサーバーで多数のスレッドが作成する必要があり、それらのスレッドのほとんどがごくわずかのスタック スペースしか使用しない場合は、スレッドの起動時に共通言語ランタイムが直ちにスレッド スタック全体をコミットしなければ、サーバーのパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4137a-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4137a-133">アンマネージ ホストは、 `STARTUP_DISABLE_COMMITTHREADSTACK` STARTUP_FLAGS [列挙体の](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 起動フラグを使用することにより、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="4137a-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4137a-134">例</span><span class="sxs-lookup"><span data-stu-id="4137a-134">Example</span></span>  
 <span data-ttu-id="4137a-135">次の例は、共通言語ランタイムの既定の動作 (スレッド起動時にスレッド スタック全体をコミット) を無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4137a-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4137a-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4137a-136">See also</span></span>

- [<span data-ttu-id="4137a-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4137a-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="4137a-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4137a-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

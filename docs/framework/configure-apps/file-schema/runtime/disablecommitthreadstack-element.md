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
ms.openlocfilehash: f717f57fe8670b126ed1468713a2114aaa772762
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198991"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="73b39-102">\<disableCommitThreadStack> 要素</span><span class="sxs-lookup"><span data-stu-id="73b39-102">\<disableCommitThreadStack> Element</span></span>

<span data-ttu-id="73b39-103">スレッドの起動時にスレッド スタック全体をコミットするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="73b39-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="73b39-104">構文</span><span class="sxs-lookup"><span data-stu-id="73b39-104">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73b39-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="73b39-105">Attributes and Elements</span></span>  

 <span data-ttu-id="73b39-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="73b39-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73b39-107">属性</span><span class="sxs-lookup"><span data-stu-id="73b39-107">Attributes</span></span>  
  
|<span data-ttu-id="73b39-108">属性</span><span class="sxs-lookup"><span data-stu-id="73b39-108">Attribute</span></span>|<span data-ttu-id="73b39-109">説明</span><span class="sxs-lookup"><span data-stu-id="73b39-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73b39-110">enabled</span><span class="sxs-lookup"><span data-stu-id="73b39-110">enabled</span></span>|<span data-ttu-id="73b39-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="73b39-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="73b39-112">スレッド起動時にスレッド スタック全体をコミットすること (既定の動作) を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="73b39-112">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="73b39-113">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="73b39-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="73b39-114">値</span><span class="sxs-lookup"><span data-stu-id="73b39-114">Value</span></span>|<span data-ttu-id="73b39-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="73b39-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73b39-116">0</span><span class="sxs-lookup"><span data-stu-id="73b39-116">0</span></span>|<span data-ttu-id="73b39-117">共通言語ランタイムの既定の動作 (スレッドの起動時にスレッド スタック全体をコミット) を無効にしません。</span><span class="sxs-lookup"><span data-stu-id="73b39-117">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="73b39-118">1</span><span class="sxs-lookup"><span data-stu-id="73b39-118">1</span></span>|<span data-ttu-id="73b39-119">共通言語ランタイムの既定の動作 (スレッドの起動時にスレッド スタック全体をコミット) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="73b39-119">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73b39-120">子要素</span><span class="sxs-lookup"><span data-stu-id="73b39-120">Child Elements</span></span>  

 <span data-ttu-id="73b39-121">なし。</span><span class="sxs-lookup"><span data-stu-id="73b39-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73b39-122">親要素</span><span class="sxs-lookup"><span data-stu-id="73b39-122">Parent Elements</span></span>  
  
|<span data-ttu-id="73b39-123">要素</span><span class="sxs-lookup"><span data-stu-id="73b39-123">Element</span></span>|<span data-ttu-id="73b39-124">説明</span><span class="sxs-lookup"><span data-stu-id="73b39-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73b39-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="73b39-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="73b39-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73b39-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73b39-127">解説</span><span class="sxs-lookup"><span data-stu-id="73b39-127">Remarks</span></span>  

 <span data-ttu-id="73b39-128">共通言語ランタイムの既定の動作では、スレッドの起動時にスレッド スタック全体がコミットされます。</span><span class="sxs-lookup"><span data-stu-id="73b39-128">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="73b39-129">メモリが限られているサーバーで多数のスレッドが作成する必要があり、それらのスレッドのほとんどがごくわずかのスタック スペースしか使用しない場合は、スレッドの起動時に共通言語ランタイムが直ちにスレッド スタック全体をコミットしなければ、サーバーのパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73b39-129">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73b39-130">アンマネージ ホストは、 `STARTUP_DISABLE_COMMITTHREADSTACK` STARTUP_FLAGS [列挙体の](../../../unmanaged-api/hosting/startup-flags-enumeration.md) 起動フラグを使用することにより、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="73b39-130">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b39-131">例</span><span class="sxs-lookup"><span data-stu-id="73b39-131">Example</span></span>  

 <span data-ttu-id="73b39-132">次の例は、共通言語ランタイムの既定の動作 (スレッド起動時にスレッド スタック全体をコミット) を無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="73b39-132">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73b39-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="73b39-133">See also</span></span>

- [<span data-ttu-id="73b39-134">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="73b39-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="73b39-135">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="73b39-135">Configuration File Schema</span></span>](../index.md)

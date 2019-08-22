---
title: <ThrowUnobservedTaskExceptions> 要素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 876452a0a56d10f169526138cdbbbd153572f457
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658851"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="85de6-102">\<ThrowUnobservedTaskExceptions > 要素</span><span class="sxs-lookup"><span data-stu-id="85de6-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="85de6-103">タスクがハンドルされない例外によって実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="85de6-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="85de6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="85de6-104">\<configuration></span></span>  
<span data-ttu-id="85de6-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="85de6-105">\<runtime></span></span>  
<span data-ttu-id="85de6-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="85de6-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85de6-107">構文</span><span class="sxs-lookup"><span data-stu-id="85de6-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85de6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85de6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="85de6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85de6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85de6-110">属性</span><span class="sxs-lookup"><span data-stu-id="85de6-110">Attributes</span></span>  
  
|<span data-ttu-id="85de6-111">属性</span><span class="sxs-lookup"><span data-stu-id="85de6-111">Attribute</span></span>|<span data-ttu-id="85de6-112">説明</span><span class="sxs-lookup"><span data-stu-id="85de6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="85de6-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="85de6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="85de6-114">未処理のタスク例外が実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="85de6-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="85de6-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="85de6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="85de6-116">値</span><span class="sxs-lookup"><span data-stu-id="85de6-116">Value</span></span>|<span data-ttu-id="85de6-117">説明</span><span class="sxs-lookup"><span data-stu-id="85de6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="85de6-118">は、未処理のタスク例外の実行中のプロセスを終了しません。</span><span class="sxs-lookup"><span data-stu-id="85de6-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="85de6-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="85de6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="85de6-120">未処理のタスク例外の実行中のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="85de6-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85de6-121">子要素</span><span class="sxs-lookup"><span data-stu-id="85de6-121">Child Elements</span></span>  
 <span data-ttu-id="85de6-122">なし。</span><span class="sxs-lookup"><span data-stu-id="85de6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85de6-123">親要素</span><span class="sxs-lookup"><span data-stu-id="85de6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="85de6-124">要素</span><span class="sxs-lookup"><span data-stu-id="85de6-124">Element</span></span>|<span data-ttu-id="85de6-125">説明</span><span class="sxs-lookup"><span data-stu-id="85de6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="85de6-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="85de6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="85de6-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="85de6-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="85de6-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="85de6-128">Remarks</span></span>  
 <span data-ttu-id="85de6-129">に関連付けら<xref:System.Threading.Tasks.Task>れている例外がまだ確認されていない場合、操作がなく<xref:System.Threading.Tasks.Task.Wait%2A> 、親がアタッチ<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>されておらず、プロパティが読み取られていない場合、タスクの例外は監視されと見なされます。</span><span class="sxs-lookup"><span data-stu-id="85de6-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="85de6-130">.NET Framework 4 では、監視され例外が発生し<xref:System.Threading.Tasks.Task>たがガベージコレクションされた場合、ファイナライザーは例外をスローしてプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="85de6-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="85de6-131">プロセスの終了は、ガベージコレクションと終了処理のタイミングによって決まります。</span><span class="sxs-lookup"><span data-stu-id="85de6-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="85de6-132">開発者がタスクに基づいて非同期コードを簡単に記述できるように、.NET Framework 4.5 では、監視され例外のこの既定の動作が変更されています。</span><span class="sxs-lookup"><span data-stu-id="85de6-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="85de6-133">監視され例外が発生し<xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>てもイベントは発生しますが、既定ではプロセスは終了しません。</span><span class="sxs-lookup"><span data-stu-id="85de6-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="85de6-134">代わりに、イベントハンドラーが例外を監視しているかどうかに関係なく、イベントが発生した後に例外が無視されます。</span><span class="sxs-lookup"><span data-stu-id="85de6-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="85de6-135">.NET Framework 4.5 では、アプリケーション構成ファイルの[ \<ThrowUnobservedTaskExceptions > 要素](throwunobservedtaskexceptions-element.md)を使用して、例外をスローする .NET Framework 4 の動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="85de6-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="85de6-136">例外の動作は、次のいずれかの方法で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="85de6-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="85de6-137">環境変数`COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`) を設定する。</span><span class="sxs-lookup"><span data-stu-id="85de6-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="85de6-138">レジストリの DWORD 値 ThrowUnobservedTaskExceptions = 1 を HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\に設定します。NETFramework キー。</span><span class="sxs-lookup"><span data-stu-id="85de6-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85de6-139">例</span><span class="sxs-lookup"><span data-stu-id="85de6-139">Example</span></span>  
 <span data-ttu-id="85de6-140">次の例では、アプリケーション構成ファイルを使用して、タスクで例外のスローを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85de6-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="85de6-141">例</span><span class="sxs-lookup"><span data-stu-id="85de6-141">Example</span></span>  
 <span data-ttu-id="85de6-142">次の例では、タスクから監視され例外がスローされる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85de6-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="85de6-143">コードを正常に動作させるには、リリースされたプログラムとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de6-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="85de6-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="85de6-144">See also</span></span>

- [<span data-ttu-id="85de6-145">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="85de6-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="85de6-146">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="85de6-146">Configuration File Schema</span></span>](../index.md)

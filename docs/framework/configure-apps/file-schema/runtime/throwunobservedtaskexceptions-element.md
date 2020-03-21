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
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153816"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="0e7fa-102">\<要素>監視タスク例外</span><span class="sxs-lookup"><span data-stu-id="0e7fa-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="0e7fa-103">タスクがハンドルされない例外によって実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
<span data-ttu-id="0e7fa-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e7fa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e7fa-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e7fa-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0e7fa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>**</span><span class="sxs-lookup"><span data-stu-id="0e7fa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7fa-107">構文</span><span class="sxs-lookup"><span data-stu-id="0e7fa-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e7fa-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0e7fa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0e7fa-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e7fa-110">属性</span><span class="sxs-lookup"><span data-stu-id="0e7fa-110">Attributes</span></span>  
  
|<span data-ttu-id="0e7fa-111">属性</span><span class="sxs-lookup"><span data-stu-id="0e7fa-111">Attribute</span></span>|<span data-ttu-id="0e7fa-112">説明</span><span class="sxs-lookup"><span data-stu-id="0e7fa-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0e7fa-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0e7fa-114">ハンドルされないタスク例外が実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0e7fa-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="0e7fa-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0e7fa-116">Value</span><span class="sxs-lookup"><span data-stu-id="0e7fa-116">Value</span></span>|<span data-ttu-id="0e7fa-117">説明</span><span class="sxs-lookup"><span data-stu-id="0e7fa-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0e7fa-118">ハンドルされないタスク例外の実行中のプロセスを終了しません。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="0e7fa-119">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0e7fa-120">ハンドルされないタスク例外の実行中のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e7fa-121">子要素</span><span class="sxs-lookup"><span data-stu-id="0e7fa-121">Child Elements</span></span>  
 <span data-ttu-id="0e7fa-122">[なし] :</span><span class="sxs-lookup"><span data-stu-id="0e7fa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e7fa-123">親要素</span><span class="sxs-lookup"><span data-stu-id="0e7fa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0e7fa-124">要素</span><span class="sxs-lookup"><span data-stu-id="0e7fa-124">Element</span></span>|<span data-ttu-id="0e7fa-125">説明</span><span class="sxs-lookup"><span data-stu-id="0e7fa-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0e7fa-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0e7fa-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="0e7fa-128">解説</span><span class="sxs-lookup"><span data-stu-id="0e7fa-128">Remarks</span></span>  
 <span data-ttu-id="0e7fa-129">に関連付けられた例外<xref:System.Threading.Tasks.Task>が観測されていない場合、操作はなく<xref:System.Threading.Tasks.Task.Wait%2A>、親はアタッチされず、<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>プロパティが読み取られておらず、タスク例外は監視されないと見なされます。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="0e7fa-130">NET Framework 4 では、既定では、例外<xref:System.Threading.Tasks.Task>が発生していないがガベージ コレクションされた場合、ファイナライザーは例外をスローし、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="0e7fa-131">プロセスの終了は、ガベージ コレクションとファイナライズのタイミングによって決まります。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="0e7fa-132">開発者がタスクに基づいて非同期コードを記述しやすくするために、.NET Framework 4.5 では、例外が発生していない場合に、この既定の動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="0e7fa-133">例外が発生しても例外が発生<xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>してもイベントは発生しますが、既定ではプロセスは終了しません。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="0e7fa-134">代わりに、イベント ハンドラーが例外を監視するかどうかに関係なく、イベントが発生した後に例外は無視されます。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="0e7fa-135">NET Framework 4.5 では、アプリケーション構成ファイルの[\<ThrowUn観測TaskExceptions>要素](throwunobservedtaskexceptions-element.md)を使用して、例外をスローする .NET Framework 4 の動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="0e7fa-136">例外の動作は、次のいずれかの方法で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="0e7fa-137">環境変数`COMPlus_ThrowUnobservedTaskExceptions`を設定することにより(`set COMPlus_ThrowUnobservedTaskExceptions=1`)</span><span class="sxs-lookup"><span data-stu-id="0e7fa-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="0e7fa-138">レジストリ DWORD 値を設定することで、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft でタスク例外 =\\1 を指定します。キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e7fa-139">例</span><span class="sxs-lookup"><span data-stu-id="0e7fa-139">Example</span></span>  
 <span data-ttu-id="0e7fa-140">アプリケーション構成ファイルを使用して、タスクで例外のスローを有効にする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="0e7fa-141">例</span><span class="sxs-lookup"><span data-stu-id="0e7fa-141">Example</span></span>  
 <span data-ttu-id="0e7fa-142">次の例は、監視されていない例外がタスクからスローされる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="0e7fa-143">コードが正しく動作するには、リリース済みプログラムとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e7fa-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0e7fa-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e7fa-144">See also</span></span>

- [<span data-ttu-id="0e7fa-145">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0e7fa-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0e7fa-146">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="0e7fa-146">Configuration File Schema</span></span>](../index.md)

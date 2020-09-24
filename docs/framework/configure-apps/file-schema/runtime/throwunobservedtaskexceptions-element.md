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
ms.openlocfilehash: 012c2e70e66015bc317606a7eea07812b5df26e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183924"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="b0bb0-102">\<ThrowUnobservedTaskExceptions> 要素</span><span class="sxs-lookup"><span data-stu-id="b0bb0-102">\<ThrowUnobservedTaskExceptions> Element</span></span>

<span data-ttu-id="b0bb0-103">タスクがハンドルされない例外によって実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="b0bb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0bb0-104">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0bb0-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b0bb0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b0bb0-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0bb0-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0bb0-107">Attributes</span></span>  
  
|<span data-ttu-id="b0bb0-108">属性</span><span class="sxs-lookup"><span data-stu-id="b0bb0-108">Attribute</span></span>|<span data-ttu-id="b0bb0-109">説明</span><span class="sxs-lookup"><span data-stu-id="b0bb0-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b0bb0-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b0bb0-111">未処理のタスク例外が実行中のプロセスを終了するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-111">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b0bb0-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="b0bb0-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="b0bb0-113">値</span><span class="sxs-lookup"><span data-stu-id="b0bb0-113">Value</span></span>|<span data-ttu-id="b0bb0-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="b0bb0-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b0bb0-115">は、未処理のタスク例外の実行中のプロセスを終了しません。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-115">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="b0bb0-116">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b0bb0-117">未処理のタスク例外の実行中のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-117">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0bb0-118">子要素</span><span class="sxs-lookup"><span data-stu-id="b0bb0-118">Child Elements</span></span>  

 <span data-ttu-id="b0bb0-119">なし。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0bb0-120">親要素</span><span class="sxs-lookup"><span data-stu-id="b0bb0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0bb0-121">要素</span><span class="sxs-lookup"><span data-stu-id="b0bb0-121">Element</span></span>|<span data-ttu-id="b0bb0-122">説明</span><span class="sxs-lookup"><span data-stu-id="b0bb0-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b0bb0-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b0bb0-124">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-124">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="b0bb0-125">解説</span><span class="sxs-lookup"><span data-stu-id="b0bb0-125">Remarks</span></span>  

 <span data-ttu-id="b0bb0-126">に関連付けられている例外がまだ <xref:System.Threading.Tasks.Task> 確認されていない場合、操作がなく、親がアタッチされておらず、プロパティが読み取られていない場合 <xref:System.Threading.Tasks.Task.Wait%2A> <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 、タスクの例外は監視されと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-126">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="b0bb0-127">.NET Framework 4 では、監視され例外が発生したが <xref:System.Threading.Tasks.Task> ガベージコレクションされた場合、ファイナライザーは例外をスローしてプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-127">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="b0bb0-128">プロセスの終了は、ガベージコレクションと終了処理のタイミングによって決まります。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-128">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="b0bb0-129">開発者がタスクに基づいて非同期コードを簡単に記述できるように、.NET Framework 4.5 では、監視され例外のこの既定の動作が変更されています。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-129">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="b0bb0-130">監視され例外が発生しても <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> イベントは発生しますが、既定ではプロセスは終了しません。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-130">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="b0bb0-131">代わりに、イベントハンドラーが例外を監視しているかどうかに関係なく、イベントが発生した後に例外が無視されます。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-131">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="b0bb0-132">.NET Framework 4.5 では、アプリケーション構成ファイルの[ \<ThrowUnobservedTaskExceptions> 要素](throwunobservedtaskexceptions-element.md)を使用して、例外をスローする .NET Framework 4 つの動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-132">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="b0bb0-133">例外の動作は、次のいずれかの方法で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-133">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="b0bb0-134">環境変数 () を設定する `COMPlus_ThrowUnobservedTaskExceptions` `set COMPlus_ThrowUnobservedTaskExceptions=1` 。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-134">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="b0bb0-135">レジストリの DWORD 値 ThrowUnobservedTaskExceptions = 1 を HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft に設定し \\ ます。NETFramework キー。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-135">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0bb0-136">例</span><span class="sxs-lookup"><span data-stu-id="b0bb0-136">Example</span></span>  

 <span data-ttu-id="b0bb0-137">次の例では、アプリケーション構成ファイルを使用して、タスクで例外のスローを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-137">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="b0bb0-138">例</span><span class="sxs-lookup"><span data-stu-id="b0bb0-138">Example</span></span>  

 <span data-ttu-id="b0bb0-139">次の例では、タスクから監視され例外がスローされる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-139">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="b0bb0-140">コードを正常に動作させるには、リリースされたプログラムとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0bb0-140">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b0bb0-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0bb0-141">See also</span></span>

- [<span data-ttu-id="b0bb0-142">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b0bb0-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b0bb0-143">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b0bb0-143">Configuration File Schema</span></span>](../index.md)

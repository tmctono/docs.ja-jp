---
title: gcUnmanagedToManaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f662114868832f909d734a482e1dc9aefb841a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150881"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="d376f-102">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="d376f-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="d376f-103">`gcUnmanagedToManaged` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、スレッドがアンマネージド コードからマネージド コードに遷移する時に、毎回ガベージ コレクションが行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="d376f-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d376f-104">症状</span><span class="sxs-lookup"><span data-stu-id="d376f-104">Symptoms</span></span>  
 <span data-ttu-id="d376f-105">COM およびプラットフォーム呼び出しを使用してアンマネージ ユーザー コンポーネントを実行中のアプリケーションによって、CLR で非確定的なアクセス違反が発生します。</span><span class="sxs-lookup"><span data-stu-id="d376f-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d376f-106">原因</span><span class="sxs-lookup"><span data-stu-id="d376f-106">Cause</span></span>  
 <span data-ttu-id="d376f-107">アプリケーションがアンマネージ ユーザー コンポーネントを実行中の場合、それらのコンポーネントによって、ガベージ コレクトされたヒープが破損された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d376f-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="d376f-108">これが原因で、ガベージ コレクターがオブジェクト グラフをウォークしようとしたときに、CLR でアクセス違反が発生します。</span><span class="sxs-lookup"><span data-stu-id="d376f-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d376f-109">解像度</span><span class="sxs-lookup"><span data-stu-id="d376f-109">Resolution</span></span>  
 <span data-ttu-id="d376f-110">このアシスタントを有効にすると、各マネージド遷移の前にガベージ コレクションが必ず行われるようになるため、アンマネージド コンポーネントがガベージ コレクトされたヒープを破損してから、アクセス違反が発生するまでの時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="d376f-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d376f-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="d376f-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="d376f-112">スレッドがアンマネージド コードからマネージド コードに遷移する時に、毎回ガベージ コレクションが行われるようになります。</span><span class="sxs-lookup"><span data-stu-id="d376f-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d376f-113">出力</span><span class="sxs-lookup"><span data-stu-id="d376f-113">Output</span></span>  
 <span data-ttu-id="d376f-114">この MDA は、出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d376f-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d376f-115">構成</span><span class="sxs-lookup"><span data-stu-id="d376f-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d376f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d376f-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d376f-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="d376f-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d376f-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="d376f-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="d376f-119">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="d376f-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

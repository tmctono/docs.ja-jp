---
title: gcManagedToUnmanaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bb4779e300df71a5d075a322bcac8398ce42f34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754441"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="518aa-102">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="518aa-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="518aa-103">`gcManagedToUnmanaged` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、スレッドがマネージド コードからアンマネージド コードに遷移する時に、毎回ガベージ コレクションがなされるようにします。</span><span class="sxs-lookup"><span data-stu-id="518aa-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="518aa-104">症状</span><span class="sxs-lookup"><span data-stu-id="518aa-104">Symptoms</span></span>  
 <span data-ttu-id="518aa-105">アンマネージド ユーザー コンポーネントは、COM に公開されたマネージド オブジェクトを使おうとすると、アクセス違反をスローします。</span><span class="sxs-lookup"><span data-stu-id="518aa-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="518aa-106">COM オブジェクトはリリース済みのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="518aa-106">The COM object appears to have been released.</span></span> <span data-ttu-id="518aa-107">アクセス違反は非確定です。</span><span class="sxs-lookup"><span data-stu-id="518aa-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="518aa-108">原因</span><span class="sxs-lookup"><span data-stu-id="518aa-108">Cause</span></span>  
 <span data-ttu-id="518aa-109">アンマネージド コンポーネントがマネージド COM オブジェクトを正しくカウントする参照でない場合、ランタイムは、アンマネージド コンポーネントがオブジェクトへの参照を保持していると、COM に公開されたマネージド オブジェクトを収集できます。</span><span class="sxs-lookup"><span data-stu-id="518aa-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="518aa-110">ランタイムはガベージ コレクション中に <xref:System.Runtime.InteropServices.Marshal.Release%2A> を呼び出すので、ユーザー コンポーネントがガベージ コレクションの発生前にオブジェクトを使用すると、それは収集されないことになります。</span><span class="sxs-lookup"><span data-stu-id="518aa-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="518aa-111">これが非確定の原因です。</span><span class="sxs-lookup"><span data-stu-id="518aa-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="518aa-112">解像度</span><span class="sxs-lookup"><span data-stu-id="518aa-112">Resolution</span></span>  
 <span data-ttu-id="518aa-113">このアシスタントを有効にすると、オブジェクトが収集の対象になってから <xref:System.Runtime.InteropServices.Marshal.Release%2A> が呼び出されるまでの時間が短縮し、収集されるオブジェクトへのアクセスを最初に試みるアンマネージ コンポーネントの追跡に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="518aa-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="518aa-114">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="518aa-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="518aa-115">スレッドがマネージド コードからアンマネージド コードに遷移する時に、毎回ガベージ コレクションがなされるようになります。</span><span class="sxs-lookup"><span data-stu-id="518aa-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="518aa-116">出力</span><span class="sxs-lookup"><span data-stu-id="518aa-116">Output</span></span>  
 <span data-ttu-id="518aa-117">この MDA は、出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="518aa-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="518aa-118">構成</span><span class="sxs-lookup"><span data-stu-id="518aa-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="518aa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="518aa-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="518aa-120">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="518aa-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="518aa-121">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="518aa-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
- [<span data-ttu-id="518aa-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="518aa-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)

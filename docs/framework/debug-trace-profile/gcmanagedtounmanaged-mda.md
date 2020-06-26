---
title: gcManagedToUnmanaged MDA
description: GcManagedToUnmanaged マネージデバッグアシスタントを確認します。 この MDA は、アンマネージコードへの遷移中にガベージコレクションが途中で発生したためにアクティブになる場合があります。
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
ms.openlocfilehash: 76c621a1f2bb780d38228f2a84d4c77441774770
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415915"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="f2023-104">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="f2023-104">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="f2023-105">`gcManagedToUnmanaged` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、スレッドがマネージド コードからアンマネージド コードに遷移する時に、毎回ガベージ コレクションがなされるようにします。</span><span class="sxs-lookup"><span data-stu-id="f2023-105">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f2023-106">現象</span><span class="sxs-lookup"><span data-stu-id="f2023-106">Symptoms</span></span>  
 <span data-ttu-id="f2023-107">アンマネージド ユーザー コンポーネントは、COM に公開されたマネージド オブジェクトを使おうとすると、アクセス違反をスローします。</span><span class="sxs-lookup"><span data-stu-id="f2023-107">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="f2023-108">COM オブジェクトはリリース済みのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2023-108">The COM object appears to have been released.</span></span> <span data-ttu-id="f2023-109">アクセス違反は非確定です。</span><span class="sxs-lookup"><span data-stu-id="f2023-109">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f2023-110">原因</span><span class="sxs-lookup"><span data-stu-id="f2023-110">Cause</span></span>  
 <span data-ttu-id="f2023-111">アンマネージド コンポーネントがマネージド COM オブジェクトを正しくカウントする参照でない場合、ランタイムは、アンマネージド コンポーネントがオブジェクトへの参照を保持していると、COM に公開されたマネージド オブジェクトを収集できます。</span><span class="sxs-lookup"><span data-stu-id="f2023-111">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="f2023-112">ランタイムはガベージ コレクション中に <xref:System.Runtime.InteropServices.Marshal.Release%2A> を呼び出すので、ユーザー コンポーネントがガベージ コレクションの発生前にオブジェクトを使用すると、それは収集されないことになります。</span><span class="sxs-lookup"><span data-stu-id="f2023-112">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="f2023-113">これが非確定の原因です。</span><span class="sxs-lookup"><span data-stu-id="f2023-113">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f2023-114">解決策</span><span class="sxs-lookup"><span data-stu-id="f2023-114">Resolution</span></span>  
 <span data-ttu-id="f2023-115">このアシスタントを有効にすると、オブジェクトが収集の対象になってから <xref:System.Runtime.InteropServices.Marshal.Release%2A> が呼び出されるまでの時間が短縮し、収集されるオブジェクトへのアクセスを最初に試みるアンマネージ コンポーネントの追跡に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f2023-115">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f2023-116">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="f2023-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="f2023-117">スレッドがマネージド コードからアンマネージド コードに遷移する時に、毎回ガベージ コレクションがなされるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2023-117">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f2023-118">出力</span><span class="sxs-lookup"><span data-stu-id="f2023-118">Output</span></span>  
 <span data-ttu-id="f2023-119">この MDA は、出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="f2023-119">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f2023-120">構成</span><span class="sxs-lookup"><span data-stu-id="f2023-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2023-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2023-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f2023-122">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="f2023-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f2023-123">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="f2023-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="f2023-124">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="f2023-124">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)

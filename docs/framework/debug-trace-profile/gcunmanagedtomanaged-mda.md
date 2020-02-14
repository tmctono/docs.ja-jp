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
ms.openlocfilehash: dd4080870ae88da8d4e2055369cd36f3981f2eac
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216454"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="8a420-102">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="8a420-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="8a420-103">`gcUnmanagedToManaged` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、スレッドがアンマネージド コードからマネージド コードに遷移する時に、毎回ガベージ コレクションが行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a420-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8a420-104">現象</span><span class="sxs-lookup"><span data-stu-id="8a420-104">Symptoms</span></span>  
 <span data-ttu-id="8a420-105">COM およびプラットフォーム呼び出しを使用してアンマネージ ユーザー コンポーネントを実行中のアプリケーションによって、CLR で非確定的なアクセス違反が発生します。</span><span class="sxs-lookup"><span data-stu-id="8a420-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8a420-106">原因</span><span class="sxs-lookup"><span data-stu-id="8a420-106">Cause</span></span>  
 <span data-ttu-id="8a420-107">アプリケーションがアンマネージ ユーザー コンポーネントを実行中の場合、それらのコンポーネントによって、ガベージ コレクトされたヒープが破損された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a420-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="8a420-108">これが原因で、ガベージ コレクターがオブジェクト グラフをウォークしようとしたときに、CLR でアクセス違反が発生します。</span><span class="sxs-lookup"><span data-stu-id="8a420-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8a420-109">解決策</span><span class="sxs-lookup"><span data-stu-id="8a420-109">Resolution</span></span>  
 <span data-ttu-id="8a420-110">このアシスタントを有効にすると、各マネージド遷移の前にガベージ コレクションが必ず行われるようになるため、アンマネージド コンポーネントがガベージ コレクトされたヒープを破損してから、アクセス違反が発生するまでの時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="8a420-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8a420-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="8a420-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="8a420-112">スレッドがアンマネージド コードからマネージド コードに遷移する時に、毎回ガベージ コレクションが行われるようになります。</span><span class="sxs-lookup"><span data-stu-id="8a420-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8a420-113">出力</span><span class="sxs-lookup"><span data-stu-id="8a420-113">Output</span></span>  
 <span data-ttu-id="8a420-114">この MDA は、出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="8a420-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8a420-115">構成</span><span class="sxs-lookup"><span data-stu-id="8a420-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a420-116">参照</span><span class="sxs-lookup"><span data-stu-id="8a420-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8a420-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="8a420-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8a420-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="8a420-118">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="8a420-119">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="8a420-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)

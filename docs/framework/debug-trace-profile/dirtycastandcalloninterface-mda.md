---
title: dirtyCastAndCallOnInterface MDA
description: Dirtycaスタンド Calloninterface マネージデバッグアシスタントを確認します。これは、事前バインディングされた vtable 呼び出しが遅延バインディングのみのクラスインターフェイスで実行されるときに呼び出されます。
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
ms.openlocfilehash: 2ed5589909915a261a22c48490e469ae52659c8c
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416071"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="05ccf-103">dirtyCastAndCallOnInterface MDA</span><span class="sxs-lookup"><span data-stu-id="05ccf-103">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="05ccf-104">`dirtyCastAndCallOnInterface` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、vtable を使用して事前バインディングされた呼び出しが、遅延バインディング専用とマークされたクラス インターフェイスで試行されたときにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="05ccf-104">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="05ccf-105">現象</span><span class="sxs-lookup"><span data-stu-id="05ccf-105">Symptoms</span></span>  
 <span data-ttu-id="05ccf-106">COM 経由で CLR への事前バインディングされた呼び出しが実行されると、アプリケーションはアクセス違反をスローするか、予期しない動作に発生します。</span><span class="sxs-lookup"><span data-stu-id="05ccf-106">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="05ccf-107">原因</span><span class="sxs-lookup"><span data-stu-id="05ccf-107">Cause</span></span>  
 <span data-ttu-id="05ccf-108">コードは、遅延バインディング専用のクラス インターフェイス経由で、vtable を使用して事前バインディングされた呼び出しを試行しています。</span><span class="sxs-lookup"><span data-stu-id="05ccf-108">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="05ccf-109">既定では、クラス インターフェイスは遅延バインディング専用として識別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="05ccf-109">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="05ccf-110">また、<xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 属性に <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> 値 (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`) が設定されている場合も、遅延バインディングとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="05ccf-110">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="05ccf-111">解決策</span><span class="sxs-lookup"><span data-stu-id="05ccf-111">Resolution</span></span>  
 <span data-ttu-id="05ccf-112">推奨される解決策としては、COM で使用するための明示的なインターフェイスを定義し、自動生成されるクラス インターフェイスを通してではなく、このインターフェイスを通して、COM クライアント呼び出しを実行するようにする方法があります。</span><span class="sxs-lookup"><span data-stu-id="05ccf-112">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="05ccf-113">代わりに、`IDispatch` を介して、COM からの呼び出しを遅延バインディングされた呼び出しに変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="05ccf-113">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="05ccf-114">事前バインディングされた呼び出しを COM から実行できるように、クラスを <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) として識別することもできます。ただし、「<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>」に記載されているバージョン管理の制約から、<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> を使用しないことを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="05ccf-114">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="05ccf-115">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="05ccf-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="05ccf-116">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="05ccf-116">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="05ccf-117">遅延バインディングされたインターフェイス上の事前バインディングされた呼び出しに関するデータを報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="05ccf-117">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="05ccf-118">出力</span><span class="sxs-lookup"><span data-stu-id="05ccf-118">Output</span></span>  
 <span data-ttu-id="05ccf-119">事前バインディングでアクセスされたメソッド名またはフィールド名です。</span><span class="sxs-lookup"><span data-stu-id="05ccf-119">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="05ccf-120">構成</span><span class="sxs-lookup"><span data-stu-id="05ccf-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="05ccf-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="05ccf-121">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="05ccf-122">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="05ccf-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)

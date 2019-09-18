---
title: pInvokeStackImbalance MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc4a48c79fc39b12f8231bd913b4ca8970c0f46f
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052364"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="de29c-102">PInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="de29c-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="de29c-103">マネージデバッグアシスタント (MDA) は、プラットフォーム呼び出しの後のスタックの深さが、予想されるスタックの深さと一致しないことを CLR が検出したときに<xref:System.Runtime.InteropServices.DllImportAttribute>アクティブ化されます。これには、属性で指定した呼び出し規約と、 `PInvokeStackImbalance`マネージシグネチャ内のパラメーターの宣言。</span><span class="sxs-lookup"><span data-stu-id="de29c-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="de29c-104">`PInvokeStackImbalance` MDA は 32 ビット x86 プラットフォームに対してのみ実装されています。</span><span class="sxs-lookup"><span data-stu-id="de29c-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="de29c-105">MDA `PInvokeStackImbalance`は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="de29c-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="de29c-106">Visual Studio 2017 では、 `PInvokeStackImbalance` **[例外設定]** ダイアログボックスの **[マネージデバッグアシスタント]** の一覧に MDA が表示されます > ([**Windows**  >  **のデバッグ] を選択すると表示されます)。例外設定**)。</span><span class="sxs-lookup"><span data-stu-id="de29c-106">In Visual Studio 2017, The `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="de29c-107">ただし、[スローされ**たときに中断**する] チェックボックスをオンまたはオフにしても、MDA は有効または無効になりません。MDA がアクティブになったときに Visual Studio が例外をスローするかどうかのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="de29c-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="de29c-108">症状</span><span class="sxs-lookup"><span data-stu-id="de29c-108">Symptoms</span></span>

<span data-ttu-id="de29c-109">プラットフォーム呼び出しの実行時または実行後に、アプリケーションでアクセス違反またはメモリ破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="de29c-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="de29c-110">原因</span><span class="sxs-lookup"><span data-stu-id="de29c-110">Cause</span></span>

<span data-ttu-id="de29c-111">プラットフォーム呼び出しのマネージド シグネチャが、呼び出されているメソッドのアンマネージド シグネチャと一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de29c-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="de29c-112">この不一致は、正しい数のパラメーターを宣言しないか、適切なサイズのパラメーターを指定しないマネージド シグネチャで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de29c-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="de29c-113">また、<xref:System.Runtime.InteropServices.DllImportAttribute> 属性によって指定されている可能性がある呼び出し規則が、アンマネージ呼び出し規則と一致しない場合にも、MDA がアクティブ化される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de29c-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="de29c-114">解決策</span><span class="sxs-lookup"><span data-stu-id="de29c-114">Resolution</span></span>

<span data-ttu-id="de29c-115">マネージド プラットフォーム呼び出しシグネチャ、および呼び出し規則を確認して、ネイティブ ターゲットのシグネチャと呼び出し規則に一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="de29c-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="de29c-116">マネージド側とアンマネージド側の両方で、呼び出し規則を明示的に指定してください。</span><span class="sxs-lookup"><span data-stu-id="de29c-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="de29c-117">また、あまり可能性はありませんが、アンマネージ コンパイラのバグなど、何らかの理由によりアンマネージ関数でスタックの不均衡が発生している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="de29c-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="de29c-118">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="de29c-118">Effect on the Runtime</span></span>

<span data-ttu-id="de29c-119">すべてのプラットフォーム呼び出しが、CLR の最適化されていないパスを取得するよう強制します。</span><span class="sxs-lookup"><span data-stu-id="de29c-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="de29c-120">出力</span><span class="sxs-lookup"><span data-stu-id="de29c-120">Output</span></span>

<span data-ttu-id="de29c-121">MDA メッセージが、スタックの不均衡の原因であるプラットフォーム呼び出しメソッド呼び出しの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="de29c-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="de29c-122">メソッド `SampleMethod` のプラットフォーム呼び出しのサンプル メッセージは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de29c-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="de29c-123">**PInvoke 関数 ' SampleMethod ' の呼び出しがスタックを不均衡にしました。マネージ PInvoke 署名がアンマネージターゲットシグネチャと一致しないことが原因である可能性があります。PInvoke 署名の呼び出し規約とパラメーターが、ターゲットのアンマネージシグネチャと一致することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="de29c-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="de29c-124">構成</span><span class="sxs-lookup"><span data-stu-id="de29c-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="de29c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="de29c-125">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="de29c-126">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="de29c-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="de29c-127">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="de29c-127">Interop Marshaling</span></span>](../interop/interop-marshaling.md)

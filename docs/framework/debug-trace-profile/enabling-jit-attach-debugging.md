---
title: JIT アタッチ デバッグの有効化
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005395beabd956767b59e0cebd563fe883f6fe53
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489798"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="17a44-102">JIT アタッチ デバッグの有効化</span><span class="sxs-lookup"><span data-stu-id="17a44-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="17a44-103">JIT アタッチ デバッグとは、エラーが発生したとき、または特定のメソッドまたは関数によってトリガーすることで、プロセスにデバッガーをアタッチすることを表すために使用される語句です。</span><span class="sxs-lookup"><span data-stu-id="17a44-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="17a44-104">JIT アタッチ デバッグは、次のエラー状態で使用されます。</span><span class="sxs-lookup"><span data-stu-id="17a44-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="17a44-105">未処理の例外 (ネイティブ コードとマネージド コードの両方)。</span><span class="sxs-lookup"><span data-stu-id="17a44-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="17a44-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> メソッドまたは [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) 関数 (Windows 7 ファミリ)。</span><span class="sxs-lookup"><span data-stu-id="17a44-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="17a44-107">実行時の致命的なエラー。</span><span class="sxs-lookup"><span data-stu-id="17a44-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="17a44-108">JIT アタッチ デバッグは、次のメソッドや関数への呼び出しによってもトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="17a44-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="17a44-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> メソッド</span><span class="sxs-lookup"><span data-stu-id="17a44-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="17a44-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> メソッド</span><span class="sxs-lookup"><span data-stu-id="17a44-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="17a44-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) 関数 (Win32)。</span><span class="sxs-lookup"><span data-stu-id="17a44-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="17a44-112">.NET Framework 4 では、前に、.NET Framework には、ネイティブおよびマネージ デバッガーの動作を制御する別々 のレジストリ キーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="17a44-112">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="17a44-113">以降、.NET Framework 4 では、コントロールが 1 つのレジストリ キーの下で統合します。Hkey_local_machine \software\microsoft\windows \current Version\AeDebug します。</span><span class="sxs-lookup"><span data-stu-id="17a44-113">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="17a44-114">このキーに設定できる値により、デバッガーを呼び出すかどうか、呼び出す場合は、ユーザーの操作を必要とするダイアログ ボックスによって呼び出すかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="17a44-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="17a44-115">このレジストリ キーの設定方法の詳細については、次を参照してください。[自動デバッグ構成](https://go.microsoft.com/fwlink/?LinkId=181767)します。</span><span class="sxs-lookup"><span data-stu-id="17a44-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a44-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="17a44-116">See also</span></span>

- [<span data-ttu-id="17a44-117">デバッグ、トレース、およびプロファイリング</span><span class="sxs-lookup"><span data-stu-id="17a44-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
- [<span data-ttu-id="17a44-118">イメージのデバッグの簡略化</span><span class="sxs-lookup"><span data-stu-id="17a44-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)

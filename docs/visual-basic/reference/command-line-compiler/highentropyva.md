---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 58026ff84f1ff501bf767adebcfc01f7de5bf4a4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005584"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="5d967-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d967-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="5d967-103">64ビットの実行可能ファイル、または[/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)コンパイラオプションによってマークされた実行可能ファイルが、高エントロピアドレス空間レイアウトのランダム化 (ASLR) をサポートするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5d967-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d967-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d967-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d967-105">引数</span><span class="sxs-lookup"><span data-stu-id="5d967-105">Arguments</span></span>  
 <span data-ttu-id="5d967-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5d967-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="5d967-107">任意。</span><span class="sxs-lookup"><span data-stu-id="5d967-107">Optional.</span></span> <span data-ttu-id="5d967-108">このオプションは、既定ではオフになっています。または、`-highentropyva-` を指定した場合はです。</span><span class="sxs-lookup"><span data-stu-id="5d967-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="5d967-109">@No__t-0 または `-highentropyva+` を指定した場合、オプションは on になります。</span><span class="sxs-lookup"><span data-stu-id="5d967-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d967-110">コメント</span><span class="sxs-lookup"><span data-stu-id="5d967-110">Remarks</span></span>  
 <span data-ttu-id="5d967-111">このオプションを指定すると、カーネルが ASLR の一部としてプロセスのアドレス空間レイアウトをランダムに処理したときに、互換性のあるバージョンの Windows カーネルでエントロピを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d967-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="5d967-112">カーネルがより高いエントロピを使用する場合は、スタックやヒープなどのメモリ領域により多くのアドレスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5d967-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="5d967-113">これによって特定のメモリ領域の位置を推測しづらくなる効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="5d967-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="5d967-114">このオプションが on に設定されている場合、ターゲットの実行可能ファイルとそれが依存するモジュールは、これらのモジュールが64ビットプロセスとして実行されている場合、4ギガバイト (GB) を超えるポインター値を処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d967-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d967-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d967-115">See also</span></span>

- [<span data-ttu-id="5d967-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5d967-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5d967-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="5d967-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775653"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="0d00b-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d00b-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="0d00b-103">64ビットの実行可能ファイルまたは[-platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)コンパイラオプションによってマークされた実行可能ファイルが、高エントロピアドレス空間レイアウトのランダム化 (ASLR) をサポートするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0d00b-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d00b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d00b-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d00b-105">引数</span><span class="sxs-lookup"><span data-stu-id="0d00b-105">Arguments</span></span>  
 <span data-ttu-id="0d00b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0d00b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0d00b-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0d00b-107">Optional.</span></span> <span data-ttu-id="0d00b-108">このオプションは、既定ではオフになっています。また、`-highentropyva-` を指定した場合はです。</span><span class="sxs-lookup"><span data-stu-id="0d00b-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="0d00b-109">@No__t_0 または `-highentropyva+` を指定した場合、オプションは on になります。</span><span class="sxs-lookup"><span data-stu-id="0d00b-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d00b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d00b-110">Remarks</span></span>  
 <span data-ttu-id="0d00b-111">このオプションを指定すると、カーネルが ASLR の一部としてプロセスのアドレス空間レイアウトをランダムに処理したときに、互換性のあるバージョンの Windows カーネルでエントロピを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d00b-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="0d00b-112">カーネルがより高いエントロピを使用する場合は、スタックやヒープなどのメモリ領域により多くのアドレスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0d00b-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="0d00b-113">これによって特定のメモリ領域の位置を推測しづらくなる効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="0d00b-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="0d00b-114">このオプションが on に設定されている場合、ターゲットの実行可能ファイルとそれが依存するモジュールは、これらのモジュールが64ビットプロセスとして実行されている場合、4ギガバイト (GB) を超えるポインター値を処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d00b-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d00b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d00b-115">See also</span></span>

- [<span data-ttu-id="0d00b-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="0d00b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0d00b-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="0d00b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

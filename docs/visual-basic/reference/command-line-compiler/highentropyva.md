---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 16bfea37a5742ac5aaaabfacdcf03a2b5bedb6db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663272"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="a24c3-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a24c3-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="a24c3-103">示す、64 ビット実行可能ファイルまたは実行可能ファイルでマークされているかどうか、 [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)コンパイラ オプションで高エントロピ アドレス空間レイアウト Randomization (ASLR) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a24c3-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24c3-104">構文</span><span class="sxs-lookup"><span data-stu-id="a24c3-104">Syntax</span></span>  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a24c3-105">引数</span><span class="sxs-lookup"><span data-stu-id="a24c3-105">Arguments</span></span>  
 <span data-ttu-id="a24c3-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a24c3-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="a24c3-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a24c3-107">Optional.</span></span> <span data-ttu-id="a24c3-108">既定では、オプションはオフですまたは指定した`-highentropyva-`します。</span><span class="sxs-lookup"><span data-stu-id="a24c3-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="a24c3-109">指定したかどうかに、オプションは、`-highentropyva`または`-highentropyva+`します。</span><span class="sxs-lookup"><span data-stu-id="a24c3-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a24c3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a24c3-110">Remarks</span></span>  
 <span data-ttu-id="a24c3-111">このオプションを指定する場合、互換性のあるバージョンの Windows カーネルはカーネル ASLR の一環として、プロセスのアドレス空間レイアウトをランダムにときに高いレベルのエントロピを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a24c3-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="a24c3-112">カーネルは、高いレベルのエントロピを使用している場合、アドレスの数が多いがスタックやヒープといったメモリ領域に割り当てられたことができます。</span><span class="sxs-lookup"><span data-stu-id="a24c3-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="a24c3-113">これによって特定のメモリ領域の位置を推測しづらくなる効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="a24c3-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="a24c3-114">オプションが、ターゲットの実行可能ファイルとすべてのモジュールでのこれらのモジュールは、64 ビット プロセスとして実行しているときに、4 ギガバイト (GB) を超えるポインター値を処理することに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a24c3-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24c3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a24c3-115">See also</span></span>

- [<span data-ttu-id="a24c3-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a24c3-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a24c3-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a24c3-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 9501ea46eb13baa171208e20d0c9645d118c4301
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408622"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="344b9-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="344b9-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="344b9-103">64 ビットの実行可能ファイルまたは [platform:anycpu](platform.md) コンパイラ オプションによってマークされた実行可能ファイルが、高エントロピ Address Space Layout Randomization (ASLR) をサポートするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="344b9-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="344b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="344b9-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="344b9-105">引数</span><span class="sxs-lookup"><span data-stu-id="344b9-105">Arguments</span></span>  
 <span data-ttu-id="344b9-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="344b9-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="344b9-107">任意。</span><span class="sxs-lookup"><span data-stu-id="344b9-107">Optional.</span></span> <span data-ttu-id="344b9-108">このオプションは、既定でまたは `-highentropyva-` を指定した場合はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="344b9-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="344b9-109">`-highentropyva` または `-highentropyva+` を指定した場合、オプションはオンになります。</span><span class="sxs-lookup"><span data-stu-id="344b9-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="344b9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="344b9-110">Remarks</span></span>  
 <span data-ttu-id="344b9-111">このオプションを指定すると、適合するバージョンの Windows カーネルで、ASLR の一環としてプロセスのアドレス空間レイアウトをカーネルでランダム化する際、より高いエントロピを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="344b9-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="344b9-112">カーネルでより高いエントロピが使用される場合は、スタックやヒープなどのメモリ領域により多くのアドレスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="344b9-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="344b9-113">これによって特定のメモリ領域の位置を推測しづらくなる効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="344b9-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="344b9-114">このオプションがオンになっている場合、ターゲットの実行可能ファイルとそれが依存するモジュールは、これらのモジュールが 64 ビット プロセスとして実行されている際に、4 ギガバイト (GB) を超えるポインター値を処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="344b9-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344b9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="344b9-115">See also</span></span>

- [<span data-ttu-id="344b9-116">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="344b9-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="344b9-117">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="344b9-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

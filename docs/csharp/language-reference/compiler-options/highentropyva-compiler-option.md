---
description: -highentropyva (C# コンパイラ オプション)
title: -highentropyva (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: 2c2e2780693a89072c4bb55b318be94089bf3ced
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125658"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="8f432-103">-highentropyva (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="8f432-103">-highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="8f432-104">**-highentropyva** コンパイラ オプションは、特定の実行可能ファイルで高エントロピ ASLR (Address Space Layout Randomization) をサポートするかどうかを Windows カーネルに示します。</span><span class="sxs-lookup"><span data-stu-id="8f432-104">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f432-105">構文</span><span class="sxs-lookup"><span data-stu-id="8f432-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8f432-106">引数</span><span class="sxs-lookup"><span data-stu-id="8f432-106">Arguments</span></span>  
 <span data-ttu-id="8f432-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8f432-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="8f432-108">このオプションは、64 ビットの実行可能ファイルまたは [-platform:anycpu](./platform-compiler-option.md) コンパイラ オプションによって示される実行可能ファイルで、高エントロピ仮想アドレス空間をサポートすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f432-108">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="8f432-109">既定では、このオプションが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8f432-109">The option is disabled by default.</span></span> <span data-ttu-id="8f432-110">有効にするには、**-highentropyva+** または **-highentropyva** を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8f432-110">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f432-111">注釈</span><span class="sxs-lookup"><span data-stu-id="8f432-111">Remarks</span></span>  
 <span data-ttu-id="8f432-112">**-highentropyva** オプションを指定すると、適合するバージョンの Windows カーネルで、ASLR の一環としてプロセスのアドレス空間レイアウトをランダム化する際、より高いエントロピを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8f432-112">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="8f432-113">より高いエントロピを使うということは、スタックやヒープといったメモリ領域に割り当てることのできるアドレス数が増えることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8f432-113">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="8f432-114">これによって特定のメモリ領域の位置を推測しづらくなる効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="8f432-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="8f432-115">**-highentropyva** コンパイラ オプションが指定された場合、対象となる実行可能ファイルとその依存モジュールは、64 ビット プロセスとして動作する際に 4 ギガバイト (GB) を超えるポインター値を処理できることが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f432-115">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>

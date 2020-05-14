---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005369"
---
# <a name="-optimize"></a><span data-ttu-id="c52f4-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="c52f4-102">-optimize</span></span>
<span data-ttu-id="c52f4-103">コンパイラ最適化を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c52f4-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c52f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="c52f4-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c52f4-105">引数</span><span class="sxs-lookup"><span data-stu-id="c52f4-105">Arguments</span></span>  
  
|<span data-ttu-id="c52f4-106">用語</span><span class="sxs-lookup"><span data-stu-id="c52f4-106">Term</span></span>|<span data-ttu-id="c52f4-107">定義</span><span class="sxs-lookup"><span data-stu-id="c52f4-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c52f4-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c52f4-108">`+` &#124; `-`</span></span>|<span data-ttu-id="c52f4-109">任意。</span><span class="sxs-lookup"><span data-stu-id="c52f4-109">Optional.</span></span> <span data-ttu-id="c52f4-110">`-optimize-` オプションにより、コンパイラ最適化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c52f4-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="c52f4-111">`-optimize+` オプションにより、最適化が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c52f4-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="c52f4-112">既定では、最適化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c52f4-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c52f4-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c52f4-113">Remarks</span></span>  
 <span data-ttu-id="c52f4-114">コンパイラを最適化すると、出力ファイルのサイズが小さくなり、動作が速くなり、処理の効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="c52f4-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="c52f4-115">ただし、最適化によって出力ファイル内のコードの配置が変更されるため、`-optimize+` を使用するとデバッグが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c52f4-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="c52f4-116">`-target:module` で生成されるアセンブリのすべてのモジュールには、アセンブリと同じ `-optimize` 設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c52f4-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="c52f4-117">詳細については、「[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c52f4-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="c52f4-118">`-optimize` オプションと `-debug` オプションを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c52f4-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="c52f4-119">Visual Studio 統合開発環境で -optimize を設定するには</span><span class="sxs-lookup"><span data-stu-id="c52f4-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c52f4-120">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="c52f4-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c52f4-121">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c52f4-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="c52f4-122">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c52f4-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c52f4-123">3. **[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c52f4-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="c52f4-124">4. **[最適化を有効にする]** チェック ボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="c52f4-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c52f4-125">例</span><span class="sxs-lookup"><span data-stu-id="c52f4-125">Example</span></span>  
 <span data-ttu-id="c52f4-126">次のコードでは、`T2.vb` がコンパイルされ、コンパイラの最適化が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c52f4-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="c52f4-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c52f4-127">See also</span></span>

- [<span data-ttu-id="c52f4-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c52f4-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c52f4-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c52f4-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="c52f4-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="c52f4-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="c52f4-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c52f4-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)

---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397442"
---
# <a name="-optimize"></a><span data-ttu-id="a021f-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="a021f-102">-optimize</span></span>
<span data-ttu-id="a021f-103">コンパイラ最適化を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a021f-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a021f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a021f-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a021f-105">引数</span><span class="sxs-lookup"><span data-stu-id="a021f-105">Arguments</span></span>  
  
|<span data-ttu-id="a021f-106">用語</span><span class="sxs-lookup"><span data-stu-id="a021f-106">Term</span></span>|<span data-ttu-id="a021f-107">定義</span><span class="sxs-lookup"><span data-stu-id="a021f-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="a021f-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a021f-108">`+` &#124; `-`</span></span>|<span data-ttu-id="a021f-109">任意。</span><span class="sxs-lookup"><span data-stu-id="a021f-109">Optional.</span></span> <span data-ttu-id="a021f-110">`-optimize-` オプションにより、コンパイラ最適化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="a021f-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="a021f-111">`-optimize+` オプションにより、最適化が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a021f-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="a021f-112">既定では、最適化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="a021f-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a021f-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="a021f-113">Remarks</span></span>  
 <span data-ttu-id="a021f-114">コンパイラを最適化すると、出力ファイルのサイズが小さくなり、動作が速くなり、処理の効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="a021f-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="a021f-115">ただし、最適化によって出力ファイル内のコードの配置が変更されるため、`-optimize+` を使用するとデバッグが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a021f-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="a021f-116">`-target:module` で生成されるアセンブリのすべてのモジュールには、アセンブリと同じ `-optimize` 設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a021f-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="a021f-117">詳細については、「[-target (Visual Basic)](target.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a021f-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="a021f-118">`-optimize` オプションと `-debug` オプションを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="a021f-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="a021f-119">Visual Studio 統合開発環境で -optimize を設定するには</span><span class="sxs-lookup"><span data-stu-id="a021f-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a021f-120">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a021f-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a021f-121">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a021f-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="a021f-122">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a021f-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a021f-123">3. **[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a021f-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="a021f-124">4. **[最適化を有効にする]** チェック ボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="a021f-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a021f-125">例</span><span class="sxs-lookup"><span data-stu-id="a021f-125">Example</span></span>  
 <span data-ttu-id="a021f-126">次のコードでは、`T2.vb` がコンパイルされ、コンパイラの最適化が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a021f-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="a021f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="a021f-127">See also</span></span>

- [<span data-ttu-id="a021f-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a021f-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a021f-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a021f-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="a021f-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a021f-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="a021f-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a021f-131">-target (Visual Basic)</span></span>](target.md)

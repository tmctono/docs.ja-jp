---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: d4b50d56373676bf78a7591102095209401c907d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097593"
---
# <a name="-optimize"></a><span data-ttu-id="89c70-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="89c70-102">-optimize</span></span>

<span data-ttu-id="89c70-103">コンパイラ最適化を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="89c70-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c70-104">構文</span><span class="sxs-lookup"><span data-stu-id="89c70-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="89c70-105">引数</span><span class="sxs-lookup"><span data-stu-id="89c70-105">Arguments</span></span>  
  
|<span data-ttu-id="89c70-106">期間</span><span class="sxs-lookup"><span data-stu-id="89c70-106">Term</span></span>|<span data-ttu-id="89c70-107">定義</span><span class="sxs-lookup"><span data-stu-id="89c70-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="89c70-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="89c70-108">`+` &#124; `-`</span></span>|<span data-ttu-id="89c70-109">任意。</span><span class="sxs-lookup"><span data-stu-id="89c70-109">Optional.</span></span> <span data-ttu-id="89c70-110">`-optimize-` オプションにより、コンパイラ最適化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="89c70-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="89c70-111">`-optimize+` オプションにより、最適化が有効になります。</span><span class="sxs-lookup"><span data-stu-id="89c70-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="89c70-112">既定では、最適化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="89c70-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89c70-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="89c70-113">Remarks</span></span>  

 <span data-ttu-id="89c70-114">コンパイラを最適化すると、出力ファイルのサイズが小さくなり、動作が速くなり、処理の効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="89c70-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="89c70-115">ただし、最適化によって出力ファイル内のコードの配置が変更されるため、`-optimize+` を使用するとデバッグが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89c70-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="89c70-116">`-target:module` で生成されるアセンブリのすべてのモジュールには、アセンブリと同じ `-optimize` 設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89c70-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="89c70-117">詳細については、「[-target (Visual Basic)](target.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89c70-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="89c70-118">`-optimize` オプションと `-debug` オプションを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="89c70-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="89c70-119">Visual Studio 統合開発環境で -optimize を設定するには</span><span class="sxs-lookup"><span data-stu-id="89c70-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="89c70-120">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="89c70-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="89c70-121">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c70-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="89c70-122">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c70-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="89c70-123">3. **[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c70-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="89c70-124">4. **[最適化を有効にする]** チェック ボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="89c70-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89c70-125">例</span><span class="sxs-lookup"><span data-stu-id="89c70-125">Example</span></span>  

 <span data-ttu-id="89c70-126">次のコードでは、`T2.vb` がコンパイルされ、コンパイラの最適化が有効になります。</span><span class="sxs-lookup"><span data-stu-id="89c70-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="89c70-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="89c70-127">See also</span></span>

- [<span data-ttu-id="89c70-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="89c70-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="89c70-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89c70-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="89c70-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="89c70-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="89c70-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89c70-131">-target (Visual Basic)</span></span>](target.md)

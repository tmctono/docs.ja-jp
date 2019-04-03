---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 2d14da2d0c24f3bd833503c73374d26ee73c5629
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815837"
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="12eb6-102">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12eb6-102">-nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="12eb6-103">アプリケーション マニフェストを実行可能ファイルに埋め込まないようコンパイラに指定します。</span><span class="sxs-lookup"><span data-stu-id="12eb6-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12eb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="12eb6-104">Syntax</span></span>  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="12eb6-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="12eb6-105">Remarks</span></span>  
 <span data-ttu-id="12eb6-106">このオプションを使用すると、Win32 リソース ファイルに、あるいは後のビルド ステップでアプリケーション マニフェストを指定しない限り、 Windows Vista で仮想化に従います。</span><span class="sxs-lookup"><span data-stu-id="12eb6-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="12eb6-107">仮想化について詳しくは、「[Windows Vista の ClickOnce 配置](/visualstudio/deployment/clickonce-deployment-on-windows-vista)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12eb6-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="12eb6-108">マニフェスト作成について詳しくは、「[-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12eb6-108">For more information about manifest creation, see [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12eb6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="12eb6-109">See also</span></span>

- [<span data-ttu-id="12eb6-110">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="12eb6-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- <span data-ttu-id="12eb6-111">[[アプリケーション] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="12eb6-111">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span></span>

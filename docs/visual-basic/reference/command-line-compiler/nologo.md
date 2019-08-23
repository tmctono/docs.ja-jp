---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964377"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="7a3ab-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a3ab-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="7a3ab-103">コンパイル中に著作権情報のバナーおよび情報メッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="7a3ab-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a3ab-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a3ab-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="7a3ab-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a3ab-105">Remarks</span></span>  
 <span data-ttu-id="7a3ab-106">を指定`-nologo`した場合、コンパイラは著作権情報のバナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="7a3ab-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="7a3ab-107">既定では、`-nologo` は無効です。</span><span class="sxs-lookup"><span data-stu-id="7a3ab-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a3ab-108">この`-nologo`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3ab-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a3ab-109">例</span><span class="sxs-lookup"><span data-stu-id="7a3ab-109">Example</span></span>  
 <span data-ttu-id="7a3ab-110">次のコードは`T2.vb`コンパイルされ、著作権バナーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7a3ab-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a3ab-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a3ab-111">See also</span></span>

- [<span data-ttu-id="7a3ab-112">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="7a3ab-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7a3ab-113">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="7a3ab-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

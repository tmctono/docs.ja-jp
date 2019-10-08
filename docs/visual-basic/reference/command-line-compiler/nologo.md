---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: bb64a468f67745b80b47b42c4fac18852279035d
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005430"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="73bbd-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73bbd-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="73bbd-103">コンパイル中に著作権情報のバナーおよび情報メッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="73bbd-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73bbd-104">構文</span><span class="sxs-lookup"><span data-stu-id="73bbd-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="73bbd-105">コメント</span><span class="sxs-lookup"><span data-stu-id="73bbd-105">Remarks</span></span>  
 <span data-ttu-id="73bbd-106">@No__t-0 を指定すると、コンパイラは著作権情報のバナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="73bbd-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="73bbd-107">既定では、`-nologo` は無効です。</span><span class="sxs-lookup"><span data-stu-id="73bbd-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73bbd-108">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="73bbd-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73bbd-109">例</span><span class="sxs-lookup"><span data-stu-id="73bbd-109">Example</span></span>  
 <span data-ttu-id="73bbd-110">次のコードは `T2.vb` をコンパイルし、著作権のバナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="73bbd-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="73bbd-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="73bbd-111">See also</span></span>

- [<span data-ttu-id="73bbd-112">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="73bbd-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="73bbd-113">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="73bbd-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

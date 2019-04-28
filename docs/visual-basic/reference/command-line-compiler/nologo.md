---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: c1824e4a086ecdd4b6a776bd6894f6e003d02867
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789007"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="6f73b-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f73b-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="6f73b-103">コンパイル時に著作権画面を表示および情報メッセージの表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="6f73b-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f73b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f73b-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="6f73b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f73b-105">Remarks</span></span>  
 <span data-ttu-id="6f73b-106">指定した場合`-nologo`コンパイラは著作権バナーが表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f73b-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="6f73b-107">既定では、`-nologo` は無効です。</span><span class="sxs-lookup"><span data-stu-id="6f73b-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f73b-108">`-nologo`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="6f73b-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f73b-109">例</span><span class="sxs-lookup"><span data-stu-id="6f73b-109">Example</span></span>  
 <span data-ttu-id="6f73b-110">次のコードのコンパイル`T2.vb`著作権バナーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f73b-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f73b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f73b-111">See also</span></span>

- [<span data-ttu-id="6f73b-112">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="6f73b-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6f73b-113">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="6f73b-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

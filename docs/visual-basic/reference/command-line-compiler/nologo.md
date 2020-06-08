---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: d1307603ebc06b4eb4c3786f1cd2fb432c0cf636
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360463"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="e7e19-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7e19-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="e7e19-103">コンパイル中に著作権情報のバナーおよび情報メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="e7e19-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e19-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7e19-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="e7e19-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7e19-105">Remarks</span></span>  
 <span data-ttu-id="e7e19-106">`-nologo` を指定すると、コンパイラで著作権情報のバナーが表示されません。</span><span class="sxs-lookup"><span data-stu-id="e7e19-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="e7e19-107">既定では、`-nologo` は無効です。</span><span class="sxs-lookup"><span data-stu-id="e7e19-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7e19-108">`-nologo` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7e19-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7e19-109">例</span><span class="sxs-lookup"><span data-stu-id="e7e19-109">Example</span></span>  
 <span data-ttu-id="e7e19-110">次のコードでは `T2.vb` がコンパイルされ、著作権のバナーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e7e19-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7e19-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7e19-111">See also</span></span>

- [<span data-ttu-id="e7e19-112">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="e7e19-112">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e7e19-113">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="e7e19-113">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

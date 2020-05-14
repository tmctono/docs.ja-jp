---
title: '#ExternalSource ディレクティブ'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: fa0a40827c1b3865b90c7d796ea4dd364774e1c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343830"
---
# <a name="externalsource-directive"></a><span data-ttu-id="b0603-102">#ExternalSource ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="b0603-102">#ExternalSource Directive</span></span>

<span data-ttu-id="b0603-103">ソース コードの特定の行と、ソースの外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="b0603-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0603-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0603-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="b0603-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b0603-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="b0603-106">外部ソースへのパスです。</span><span class="sxs-lookup"><span data-stu-id="b0603-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="b0603-107">外部ソースの最初の行の行番号です。</span><span class="sxs-lookup"><span data-stu-id="b0603-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="b0603-108">外部ソースでエラーが発生した行です。</span><span class="sxs-lookup"><span data-stu-id="b0603-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="b0603-109">`#ExternalSource` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="b0603-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0603-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b0603-110">Remarks</span></span>  

 <span data-ttu-id="b0603-111">このディレクティブは、コンパイラとデバッガーによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0603-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="b0603-112">ソース ファイルには、外部ソース ディレクティブを含めることができます。これは、ソース ファイル内の特定のコード行と、.aspx ファイルなどのソースの外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="b0603-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="b0603-113">コンパイル時に指定されたソース コードでエラーが発生した場合、外部ソースからのものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="b0603-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="b0603-114">外部ソース ディレクティブはコンパイルには影響しません。また、入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0603-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="b0603-115">これらはアプリケーションによる内部使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="b0603-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0603-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0603-116">See also</span></span>

- [<span data-ttu-id="b0603-117">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="b0603-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

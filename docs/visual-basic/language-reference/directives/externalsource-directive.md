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
ms.openlocfilehash: e4c7704c32c3a6c73e069d0b7129d5386696b438
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402993"
---
# <a name="externalsource-directive"></a><span data-ttu-id="22e13-102">#ExternalSource ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="22e13-102">#ExternalSource Directive</span></span>

<span data-ttu-id="22e13-103">ソース コードの特定の行と、ソースの外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="22e13-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e13-104">構文</span><span class="sxs-lookup"><span data-stu-id="22e13-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="22e13-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="22e13-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="22e13-106">外部ソースへのパスです。</span><span class="sxs-lookup"><span data-stu-id="22e13-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="22e13-107">外部ソースの最初の行の行番号です。</span><span class="sxs-lookup"><span data-stu-id="22e13-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="22e13-108">外部ソースでエラーが発生した行です。</span><span class="sxs-lookup"><span data-stu-id="22e13-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="22e13-109">`#ExternalSource` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="22e13-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22e13-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="22e13-110">Remarks</span></span>  

 <span data-ttu-id="22e13-111">このディレクティブは、コンパイラとデバッガーによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="22e13-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="22e13-112">ソース ファイルには、外部ソース ディレクティブを含めることができます。これは、ソース ファイル内の特定のコード行と、.aspx ファイルなどのソースの外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="22e13-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="22e13-113">コンパイル時に指定されたソース コードでエラーが発生した場合、外部ソースからのものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="22e13-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="22e13-114">外部ソース ディレクティブはコンパイルには影響しません。また、入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="22e13-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="22e13-115">これらはアプリケーションによる内部使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="22e13-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e13-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e13-116">See also</span></span>

- [<span data-ttu-id="22e13-117">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="22e13-117">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)

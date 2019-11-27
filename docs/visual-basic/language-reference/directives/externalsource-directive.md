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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343830"
---
# <a name="externalsource-directive"></a><span data-ttu-id="0e131-102">#ExternalSource ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="0e131-102">#ExternalSource Directive</span></span>

<span data-ttu-id="0e131-103">ソースコードの特定の行と、ソースの外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="0e131-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e131-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e131-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="0e131-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="0e131-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="0e131-106">外部ソースへのパス。</span><span class="sxs-lookup"><span data-stu-id="0e131-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="0e131-107">外部ソースの最初の行の行番号。</span><span class="sxs-lookup"><span data-stu-id="0e131-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="0e131-108">外部ソースでエラーが発生した行。</span><span class="sxs-lookup"><span data-stu-id="0e131-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="0e131-109">`#ExternalSource` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="0e131-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e131-110">コメント</span><span class="sxs-lookup"><span data-stu-id="0e131-110">Remarks</span></span>  

 <span data-ttu-id="0e131-111">このディレクティブは、コンパイラとデバッガーでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="0e131-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="0e131-112">ソースファイルには、ソースファイル内の特定のコード行と、.aspx ファイルなどのソースの外部テキストとの間のマッピングを示す、外部ソースディレクティブを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0e131-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="0e131-113">コンパイル時に指定したソースコードでエラーが発生した場合は、外部ソースからのものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="0e131-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="0e131-114">外部ソースディレクティブはコンパイルには影響しません。入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0e131-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="0e131-115">アプリケーションでの内部使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="0e131-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e131-116">参照</span><span class="sxs-lookup"><span data-stu-id="0e131-116">See also</span></span>

- [<span data-ttu-id="0e131-117">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="0e131-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

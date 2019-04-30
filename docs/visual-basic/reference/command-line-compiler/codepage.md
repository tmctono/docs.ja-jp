---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944704"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="a2ddc-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2ddc-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="a2ddc-103">コンパイルですべてのソース コード ファイルに使用するコード ページを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ddc-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2ddc-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="a2ddc-105">引数</span><span class="sxs-lookup"><span data-stu-id="a2ddc-105">Arguments</span></span>  
  
|<span data-ttu-id="a2ddc-106">用語</span><span class="sxs-lookup"><span data-stu-id="a2ddc-106">Term</span></span>|<span data-ttu-id="a2ddc-107">定義</span><span class="sxs-lookup"><span data-stu-id="a2ddc-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="a2ddc-108">必須。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-108">Required.</span></span> <span data-ttu-id="a2ddc-109">コンパイラで指定されたコード ページを使用して`id`ソース ファイルのエンコーディングを解釈します。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2ddc-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2ddc-110">Remarks</span></span>  
 <span data-ttu-id="a2ddc-111">使用することが特定のエンコーディングで保存されたソース コードをコンパイルする`-codepage`コード ページを使用する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="a2ddc-112">`-codepage`オプションは、コンパイル時にすべてのソース コード ファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="a2ddc-113">詳細については、次を参照してください。 [.NET Framework における文字エンコーディング](../../../standard/base-types/character-encoding.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="a2ddc-114">`-codepage`オプションは、シグネチャを持つ現在の ANSI コード ページ、Unicode または utf-8 を使用して、ソース コード ファイルを保存した場合は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="a2ddc-115">Visual Studio に保存既定では、すべてのソース コード ファイルが現在の ANSI コード ページで、ユーザーで別のエンコードを指定しない限り、**エンコード** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="a2ddc-116">Visual Studio を使用して、**エンコード**異なるコード ページで保存されたソース コード ファイルを開く ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2ddc-117">`-codepage`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="a2ddc-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ddc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ddc-118">See also</span></span>

- [<span data-ttu-id="a2ddc-119">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a2ddc-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

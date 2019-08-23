---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962612"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="f3a65-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3a65-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="f3a65-103">コンパイルですべてのソース コード ファイルに使用するコード ページを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3a65-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a65-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3a65-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="f3a65-105">引数</span><span class="sxs-lookup"><span data-stu-id="f3a65-105">Arguments</span></span>  
  
|<span data-ttu-id="f3a65-106">用語</span><span class="sxs-lookup"><span data-stu-id="f3a65-106">Term</span></span>|<span data-ttu-id="f3a65-107">定義</span><span class="sxs-lookup"><span data-stu-id="f3a65-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="f3a65-108">必須。</span><span class="sxs-lookup"><span data-stu-id="f3a65-108">Required.</span></span> <span data-ttu-id="f3a65-109">コンパイラは、によって指定さ`id`れたコードページを使用して、ソースファイルのエンコーディングを解釈します。</span><span class="sxs-lookup"><span data-stu-id="f3a65-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3a65-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3a65-110">Remarks</span></span>  
 <span data-ttu-id="f3a65-111">特定のエンコーディングを使用して保存されたソース`-codepage`コードをコンパイルするには、を使用して、使用するコードページを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3a65-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="f3a65-112">オプション`-codepage`は、コンパイル時にすべてのソースコードファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f3a65-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="f3a65-113">詳細については、「 [.NET Framework の文字エンコード](../../../standard/base-types/character-encoding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3a65-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="f3a65-114">ソースコードファイルが現在の ANSI コードページ、Unicode、または utf-8 を使用して署名されている場合、このオプションは必要ありません。`-codepage`</span><span class="sxs-lookup"><span data-stu-id="f3a65-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="f3a65-115">Visual Studio では、ユーザーが **[エンコード]** ダイアログボックスで別のエンコードを指定しない限り、既定では、すべてのソースコードファイルが現在の ANSI コードページと共に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f3a65-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="f3a65-116">Visual Studio では、 **[エンコード]** ダイアログボックスを使用して、別のコードページを使用して保存されたソースコードファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3a65-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3a65-117">この`-codepage`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3a65-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a65-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3a65-118">See also</span></span>

- [<span data-ttu-id="f3a65-119">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="f3a65-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

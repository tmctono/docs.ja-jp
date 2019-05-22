---
title: -codepage (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 59dc1abc3f678a4cf15543c11f9f200ff318ce8f
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876925"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="3db38-102">-codepage (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="3db38-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="3db38-103">このオプションでは、必要とするページが、システムで使用されている現在の既定のコードページでない場合に、コンパイル時に使用するコード ページを指定します。</span><span class="sxs-lookup"><span data-stu-id="3db38-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db38-104">構文</span><span class="sxs-lookup"><span data-stu-id="3db38-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="3db38-105">引数</span><span class="sxs-lookup"><span data-stu-id="3db38-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="3db38-106">コンパイル時にすべてのソース コード ファイルで使うコード ページの ID です。</span><span class="sxs-lookup"><span data-stu-id="3db38-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3db38-107">解説</span><span class="sxs-lookup"><span data-stu-id="3db38-107">Remarks</span></span>  
 <span data-ttu-id="3db38-108">コンパイラでは、まずすべてのソース ファイルを UTF-8 として解釈しようと試みられます。</span><span class="sxs-lookup"><span data-stu-id="3db38-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="3db38-109">ソース コード ファイルが UTF-8 以外のエンコーディングで、7 ビット ASCII 文字以外の文字が使われている場合は、**-codepage** オプションを使用して、使用する必要があるコード ページを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3db38-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="3db38-110">**-codepage** は、コンパイル時にすべてのソース コード ファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3db38-110">**-codepage** applies to all source code files in your compilation.</span></span>  
    
 <span data-ttu-id="3db38-111">使用しているシステムでサポートされているコード ページを確認する方法については、[GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3db38-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="3db38-112">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3db38-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db38-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3db38-113">See also</span></span>

- [<span data-ttu-id="3db38-114">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="3db38-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="3db38-115">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="3db38-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

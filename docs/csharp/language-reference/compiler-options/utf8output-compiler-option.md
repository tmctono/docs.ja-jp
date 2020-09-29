---
description: -utf8output (C# コンパイラ オプション)
title: -utf8output (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
ms.openlocfilehash: 675782ffef9768e57397e765538924b78a2abcaa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171365"
---
# <a name="-utf8output-c-compiler-options"></a><span data-ttu-id="cd007-103">-utf8output (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="cd007-103">-utf8output (C# Compiler Options)</span></span>

<span data-ttu-id="cd007-104">**-utf8output** オプションは UTF-8 エンコードを使用してコンパイラ出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="cd007-104">The **-utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd007-105">構文</span><span class="sxs-lookup"><span data-stu-id="cd007-105">Syntax</span></span>  
  
```console  
-utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd007-106">解説</span><span class="sxs-lookup"><span data-stu-id="cd007-106">Remarks</span></span>  

 <span data-ttu-id="cd007-107">国際化の設定によっては、コンパイラの出力が正しくコンソールに表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd007-107">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="cd007-108">これらの設定では、**-utf8output** を使用してコンパイラ出力をファイルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cd007-108">In these configurations, use **-utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="cd007-109">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd007-109">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd007-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd007-110">See also</span></span>

- [<span data-ttu-id="cd007-111">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="cd007-111">C# Compiler Options</span></span>](./index.md)

---
description: -preferreduilang (C# コンパイラ オプション)
title: -preferreduilang (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: f68652e910651ab5c4184376d9eb7729303382d9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124852"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="b2659-103">-preferreduilang (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="b2659-103">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="b2659-104">`-preferreduilang` コンパイラ オプションを使うと、C# コンパイラがエラー メッセージなどの出力を表示する言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2659-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2659-105">構文</span><span class="sxs-lookup"><span data-stu-id="b2659-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2659-106">引数</span><span class="sxs-lookup"><span data-stu-id="b2659-106">Arguments</span></span>  
 `language`  
 <span data-ttu-id="b2659-107">コンパイラの出力に使う言語の[言語名](/windows/desktop/Intl/language-names)。</span><span class="sxs-lookup"><span data-stu-id="b2659-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2659-108">注釈</span><span class="sxs-lookup"><span data-stu-id="b2659-108">Remarks</span></span>  
 <span data-ttu-id="b2659-109">`-preferreduilang` コンパイラ オプションを使うと、C# コンパイラがエラー メッセージおよびその他のコマンドライン出力に使う言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2659-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="b2659-110">言語の言語パックがインストールされていない場合は、オペレーティング システムの言語設定が代わりに使われ、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="b2659-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="b2659-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2659-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2659-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2659-112">See also</span></span>

- [<span data-ttu-id="b2659-113">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="b2659-113">C# Compiler Options</span></span>](./index.md)

---
title: -preferreduilang (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602561"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="c0e36-102">-preferreduilang (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="c0e36-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="c0e36-103">`-preferreduilang` コンパイラ オプションを使うと、C# コンパイラがエラー メッセージなどの出力を表示する言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0e36-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0e36-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0e36-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="c0e36-105">引数</span><span class="sxs-lookup"><span data-stu-id="c0e36-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="c0e36-106">コンパイラの出力に使う言語の[言語名](/windows/desktop/Intl/language-names)。</span><span class="sxs-lookup"><span data-stu-id="c0e36-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0e36-107">解説</span><span class="sxs-lookup"><span data-stu-id="c0e36-107">Remarks</span></span>  
 <span data-ttu-id="c0e36-108">`-preferreduilang` コンパイラ オプションを使うと、C# コンパイラがエラー メッセージおよびその他のコマンドライン出力に使う言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0e36-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="c0e36-109">言語の言語パックがインストールされていない場合は、オペレーティング システムの言語設定が代わりに使われ、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="c0e36-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="c0e36-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0e36-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e36-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0e36-111">See also</span></span>

- [<span data-ttu-id="c0e36-112">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="c0e36-112">C# Compiler Options</span></span>](./index.md)

---
title: ステートメントの終わりを指定してください。
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 169f01b02df377ba6cc21ffad53c36f5d4537140
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409648"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="2a78a-102">ステートメントの終わりを指定してください。</span><span class="sxs-lookup"><span data-stu-id="2a78a-102">End of statement expected</span></span>
<span data-ttu-id="2a78a-103">ステートメントは構文的に完全ですが、ステートメントを完了する要素の後に追加のプログラミング要素が続いています。</span><span class="sxs-lookup"><span data-stu-id="2a78a-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="2a78a-104">すべてのステートメントの末尾には、行終端記号が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a78a-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="2a78a-105">行終端記号は、Visual Basic のソース ファイルの文字を行に分割します。</span><span class="sxs-lookup"><span data-stu-id="2a78a-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="2a78a-106">行終端記号の例としては、Unicode 復帰文字 (&HD)、Unicode 改行文字 (&HA)、および Unicode 復帰文字とその後の Unicode 改行文字があります。</span><span class="sxs-lookup"><span data-stu-id="2a78a-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="2a78a-107">行終端記号の詳細については、[Visual Basic 言語の仕様](~/_vblang/spec/lexical-grammar.md#line-terminators)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a78a-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="2a78a-108">**エラー ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="2a78a-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2a78a-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2a78a-109">To correct this error</span></span>
  
1. <span data-ttu-id="2a78a-110">2 つの異なるステートメントが誤って同じ行に配置されていないかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a78a-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="2a78a-111">行終端記号を、ステートメントを完了する要素の後に挿入します。</span><span class="sxs-lookup"><span data-stu-id="2a78a-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a78a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a78a-112">See also</span></span>

- [<span data-ttu-id="2a78a-113">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="2a78a-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="2a78a-114">ステートメント</span><span class="sxs-lookup"><span data-stu-id="2a78a-114">Statements</span></span>](../../programming-guide/language-features/statements.md)

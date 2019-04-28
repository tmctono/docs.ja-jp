---
title: XML コメントの例外には 'cref' 属性を指定しなければなりません
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a974df5d2305b88946981d0d258a8088b23d3fc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766608"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="e5745-102">XML コメントの例外には 'cref' 属性を指定しなければなりません</span><span class="sxs-lookup"><span data-stu-id="e5745-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="e5745-103">\<例外 > タグは、メソッドによってスローされる可能性が例外を文書化する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5745-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="e5745-104">必要な`cref`属性は、ドキュメントのジェネレーターがチェックされているメンバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5745-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="e5745-105">メンバーが存在する場合は、ドキュメント ファイルで正規要素名に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e5745-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="e5745-106">**エラー ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="e5745-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5745-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e5745-107">To correct this error</span></span>  
  
- <span data-ttu-id="e5745-108">追加、`cref`属性、例外を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e5745-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e5745-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5745-109">See also</span></span>

- [<span data-ttu-id="e5745-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="e5745-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="e5745-111">方法: XML ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5745-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="e5745-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="e5745-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

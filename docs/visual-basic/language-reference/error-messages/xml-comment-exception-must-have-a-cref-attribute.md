---
title: XML コメントの例外には 'cref' 属性を指定しなければなりません
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592038"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="e904c-102">XML コメントの例外には 'cref' 属性を指定しなければなりません</span><span class="sxs-lookup"><span data-stu-id="e904c-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="e904c-103">@No__t 0exception > タグは、メソッドによってスローされる可能性のある例外を文書化する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e904c-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="e904c-104">必須の `cref` 属性は、ドキュメントジェネレーターによってチェックされるメンバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e904c-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="e904c-105">メンバーが存在する場合は、ドキュメントファイル内の正規要素名に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e904c-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="e904c-106">**エラー ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="e904c-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e904c-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e904c-107">To correct this error</span></span>  
  
- <span data-ttu-id="e904c-108">次のように、例外に `cref` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="e904c-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    <span data-ttu-id="e904c-109">xml</span><span class="sxs-lookup"><span data-stu-id="e904c-109">xml</span></span>  
    <span data-ttu-id="e904c-110">' ' ' の<exception cref="member">説明</exception></span><span class="sxs-lookup"><span data-stu-id="e904c-110">'''<exception cref="member">description</exception></span></span>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)

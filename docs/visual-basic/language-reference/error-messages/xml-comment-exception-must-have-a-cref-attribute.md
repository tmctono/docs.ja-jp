---
title: XML コメントの例外には 'cref' 属性を指定しなければなりません
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321171"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="0e69f-102">XML コメントの例外には 'cref' 属性を指定しなければなりません</span><span class="sxs-lookup"><span data-stu-id="0e69f-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="0e69f-103">@No__t 0exception > タグは、メソッドによってスローされる可能性のある例外を文書化する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="0e69f-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="0e69f-104">必須の `cref` 属性は、ドキュメントジェネレーターによってチェックされるメンバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e69f-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="0e69f-105">メンバーが存在する場合は、ドキュメントファイル内の正規要素名に変換されます。</span><span class="sxs-lookup"><span data-stu-id="0e69f-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="0e69f-106">**エラー ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="0e69f-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0e69f-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="0e69f-107">To correct this error</span></span>

<span data-ttu-id="0e69f-108">次のように、例外に `cref` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="0e69f-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="0e69f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e69f-109">See also</span></span>

- [<span data-ttu-id="0e69f-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="0e69f-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="0e69f-111">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="0e69f-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="0e69f-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="0e69f-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

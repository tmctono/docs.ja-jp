---
title: XML コメントの例外には 'cref' 属性を指定しなければなりません
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406509"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="b819a-102">XML コメントの例外には 'cref' 属性を指定しなければなりません</span><span class="sxs-lookup"><span data-stu-id="b819a-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="b819a-103">\<exception> タグは、メソッドによってスローされる可能性のある例外を文書化する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b819a-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="b819a-104">必須の `cref` 属性は、ドキュメント生成機能によってチェックされるメンバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b819a-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="b819a-105">メンバーが存在する場合、そのメンバーはドキュメント ファイル内の正規要素名に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b819a-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="b819a-106">**エラー ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="b819a-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b819a-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b819a-107">To correct this error</span></span>

<span data-ttu-id="b819a-108">次のように、例外に `cref` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="b819a-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="b819a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b819a-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="b819a-110">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="b819a-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="b819a-111">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="b819a-111">XML Comment Tags</span></span>](../xmldoc/index.md)

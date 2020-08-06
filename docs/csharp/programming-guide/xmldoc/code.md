---
title: <code> - C# programming guide
description: XML について説明します <code> tag. This tag is used to indicate multiple lines of code, while <c> marks single-line text in a description as code.
ms.date: 07/20/2015
f1_keywords:
- code
- <code>
helpviewer_keywords:
- code XML tag
- <code> C# XML tag
ms.assetid: f235e3bc-a709-43cf-8a9f-bd57cabdf6da
ms.openlocfilehash: f1f4cd930a876c8eca13de5f015e2b42b928d6f1
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382010"
---
# <a name="code-c-programming-guide"></a>\<code> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<code>content</code>
```

## <a name="parameters"></a>パラメーター

- `content`

  コードとしてマークするテキストです。

## <a name="remarks"></a>Remarks

`<code>` タグを使用して、複数行をコードとして指定します。 説明内の単一行テキストをコードとしてマークすることを示すには、[\<c>](./code-inline.md) を使用します。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

`<code>` タグの使用例については、[\<example>](./example.md) の記事を参照してください。

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

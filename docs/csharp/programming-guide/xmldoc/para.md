---
title: <para> - C# プログラミング ガイド
description: 'XML タグについて説明 <para> します。 このタグを使用すると、次のような別のタグのテキストに構造を追加できます: <summary>, <remarks>、または <returns>.'
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381854"
---
# <a name="para-c-programming-guide"></a>\<para> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<para>content</para>
```

## <a name="parameters"></a>パラメーター

- `content`

  段落のテキストです。

## <a name="remarks"></a>Remarks

`<para>` タグは、[\<summary>](./summary.md)、[\<remarks>](./remarks.md)、または [\<returns>](./returns.md) などのタグ内で使用します。このタグを使用すると、テキストに構造を追加することができます。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

`<para>` の使用例については、[\<summary>](./summary.md) を参照してください。

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

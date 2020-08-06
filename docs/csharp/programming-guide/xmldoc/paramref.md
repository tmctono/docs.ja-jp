---
title: <paramref> - C# プログラミング ガイド
description: XML <paramref> タグについて説明します。 このタグを使用すると、コード内の単語がパラメーターであると示すことができます。
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381841"
---
# <a name="paramref-c-programming-guide"></a>\<paramref> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<paramref name="name"/>
```

## <a name="parameters"></a>パラメーター

- `name`

  参照されるパラメーターの名前です。 名前は二重引用符 (" ") で囲みます。

## <a name="remarks"></a>Remarks

`<paramref>` タグを使用すると、`<summary>` または `<remarks>` ブロックなどのコード コメント内の単語がパラメーターを参照することを示すことができます。 この単語を、太字や斜体のフォントを使うなど、何らかの独自の方法で書式設定するために XML ファイルを処理できます。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

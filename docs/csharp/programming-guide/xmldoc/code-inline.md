---
title: <c> - C# プログラミング ガイド
description: XML <c> タグについて説明します。 このタグによって、説明内の単一行テキストをコードとしてマークできます。一方、<code> indicates multiple lines.
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 78e59e1df4b096782e0a97b6d12c21c843a1cb21
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382023"
---
# <a name="c-c-programming-guide"></a>\<c> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<c>text</c>
```

## <a name="parameters"></a>パラメーター

- `text`

  コードとして指定するテキストです。

## <a name="remarks"></a>Remarks

`<c>` タグを使用すると、説明内のテキストをコードとしてマークする必要があることを指定できます。 複数行をコードとして示す場合は、[\<code>](./code.md) を使用します。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

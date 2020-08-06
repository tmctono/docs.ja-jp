---
title: <returns> - C# プログラミング ガイド
description: XML タグについて説明 <returns> します。 このタグは、メソッド宣言のコメントで戻り値を記述するために使用されます。
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381399"
---
# <a name="returns-c-programming-guide"></a>\<returns> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<returns>description</returns>
```

## <a name="parameters"></a>パラメーター

- `description`

  戻り値の説明。

## <a name="remarks"></a>Remarks

`<returns>` タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

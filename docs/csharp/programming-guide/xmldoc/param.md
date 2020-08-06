---
title: <param> - C# プログラミング ガイド
description: XML タグについて説明 <param> します。 このタグは、メソッド宣言のコメントで、メソッドのいずれかのパラメーターを記述するために使用されます。
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: a9e3b2e86528afcbe1330788e248f0143efb5c1b
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381555"
---
# <a name="param-c-programming-guide"></a>\<param> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>パラメーター

- `name`

  メソッド パラメーターの名前です。 名前は二重引用符 (" ") で囲みます。

- `description`

  パラメーターの説明です。

## <a name="remarks"></a>Remarks

`<param>` タグは、メソッドのいずれかのパラメーターを記述するために、メソッド宣言のコメントで使用する必要があります。 複数のパラメーターをドキュメント化するには、複数の `<param>` タグを使用します。

`<param>` タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

---
title: <typeparam> - C# プログラミング ガイド
description: XML タグについて説明 <typeparam> します。 このタグは、型パラメーターを説明するために、ジェネリック型またはメソッドの宣言のコメントで使用します。
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380788"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a>パラメーター

- `name`

  型パラメーターの名前。 名前は二重引用符 (" ") で囲みます。

- `description`

  型パラメーターの説明。

## <a name="remarks"></a>Remarks

`<typeparam>` タグは、型パラメーターを説明するためにジェネリック型またはメソッドの宣言のコメントで使用する必要があります。 ジェネリック型またはメソッドの型パラメーターごとにタグを追加します。

詳細については、「[ジェネリック](../generics/index.md)」を参照してください。

`<typeparam>` タグのテキストは、IntelliSense、[オブジェクト ブラウザー ウィンドウ](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)、コード コメント Web レポートに表示されます。

コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../../language-reference/index.md)
- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

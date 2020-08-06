---
title: <include> - C# プログラミング ガイド
description: XML タグについて説明 <include> します。 このタグを使用すると、ソース コード内の型とメンバーを記述する別のファイル内のコメントを参照することができます。
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 15a99444d464594cc91a7c8805c564c703c3b608
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381906"
---
# <a name="include-c-programming-guide"></a>\<include> (C# プログラミング ガイド)

## <a name="syntax"></a>構文

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a>パラメーター

- `filename`

  文書を含む XML ファイルの名前。 ファイル名は、ソース コード ファイルの相対パスを使用して修飾することができます。 `filename` を単一引用符 (' ') で囲みます。

- `tagpath`

  タグ `name` につながる `filename` 内のタグのパス。 パスを単一引用符 (' ') で囲みます。

- `name`

  コメントの前に配置するタグの名前指定子。`name` には `id` が指定されます。

- `id`

コメントの前に配置するタグの ID。 ID は二重引用符 (" ") で囲みます。

## <a name="remarks"></a>Remarks

`<include>` タグを使用すると、ソース コード内の型とメンバーを記述する別のファイル内のコメントを参照することができます。 これは文書化のコメントをソース コード ファイル内に直接配置する方法の代替です。 別のファイルにドキュメントを配置することで、ソース コードから分離して、ソースの制御をドキュメントに適用できます。 1 人のユーザーがソース コード ファイルをチェックアウトし、他のユーザーがドキュメント ファイルをチェックアウトすることができます。

`<include>` タグは XML XPath 構文を使用します。 `<include>` の使用をカスタマイズする方法については、XPath に関するドキュメントを参照してください。

## <a name="example"></a>例

これは、複数ファイルの例です。 `<include>` を使用する最初のファイルを、次に示します。

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

2 番目のファイル *xml_include_tag.doc* には、次のドキュメント コメントが含まれています。

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>プログラムの出力

Test および Test2 クラスをコンパイルするときにコマンド ライン `-doc:DocFileName.xml.` を使うと、以下の出力が生成されます。Visual Studio では、プロジェクト デザイナーの [ビルド] ウィンドウで、XML ドキュメント コメントのオプションを指定します。 C# コンパイラが `<include>` タグを認識すると、現在のソース ファイルではなく *xml_include_tag.doc* でドキュメントのコメントを検索します。 次に、コンパイラによって *DocFileName.xml* が生成されます。これは、最終的なドキュメントを生成するために、[Sandcastle](https://github.com/EWSoftware/SHFB) などのドキュメント ツールによって使用されるファイルです。  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [ドキュメント コメントとして推奨されるタグ](./recommended-tags-for-documentation-comments.md)

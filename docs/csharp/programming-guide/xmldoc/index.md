---
title: XML ドキュメント コメント - C# プログラミング ガイド
description: XML ドキュメントのコメントについて説明します。 特別なコメント フィールドに XML 要素を含め、ご自分のコードのドキュメントを作成できます。
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: fbdeb53331d9fc63d24a3322ea13863d7c0a3630
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381880"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>XML ドキュメント コメント (C# プログラミング ガイド)

C# では、ソース コード内で、コメントの対象となるコード ブロック直前の特別なコメント フィールド (トリプル スラッシュで示す) に XML 要素を配置することで、コード用のドキュメントを作成できます。例を次に示します。

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

[-doc](../../language-reference/compiler-options/doc-compiler-option.md) オプションを使用してコンパイルすると、コンパイラは、ソース コード内のすべての XML タグを検索して、XML ドキュメント ファイルを作成します。 コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。

XML 要素を参照するには (たとえば、XML ドキュメント コメントに記述する特定の XML 要素を関数で処理する場合)、標準の引用のしくみを使用できます (`<` と `>`)。  コード参照 (`cref`) 要素でジェネリック識別子を参照するには、エスケープ文字 (たとえば、`cref="List&lt;T&gt;"`) または中かっこ (`cref="List{T}"`) を使用できます。  特殊なケースとして、コンパイラは中かっこを山かっことして解析し、ジェネリック識別子を参照するときにドキュメント コメントの編集があまり面倒にならないようにしています。

> [!NOTE]
> XML ドキュメント コメントはメタデータではなく、コンパイルされたアセンブリに含まれないため、リフレクションでアクセスできません。

## <a name="in-this-section"></a>このセクションの内容

- [ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)

- [XML ファイルの処理](./processing-the-xml-file.md)

- [ドキュメント タグの区切り記号](./delimiters-for-documentation-tags.md)

- [XML ドキュメント機能を使用する方法](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a>関連項目

詳細については次を参照してください:

- [-doc (ドキュメント コメントの処理)](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)

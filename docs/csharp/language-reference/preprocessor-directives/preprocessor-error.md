---
description: '#error - C# リファレンス'
title: '#error - C# リファレンス'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138099"
---
# <a name="error-c-reference"></a>#error (C# リファレンス)

`#error` を使用すると、コード内の特定の場所からユーザー定義の [CS1029](../compiler-messages/cs1029.md) エラーを生成できます。 次に例を示します。

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> コンパイラは `#error version` を特別な方法で処理し、使用されているコンパイラと言語バージョンを含むメッセージと共にコンパイラ エラー CS8304 を報告します。

## <a name="remarks"></a>注釈

`#error` は条件付きディレクティブ内で一般的に使用されます。

[#warning](./preprocessor-warning.md) を使用してユーザー定義の警告を生成することもできます。

## <a name="example"></a>例

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# プリプロセッサ ディレクティブ](./index.md)

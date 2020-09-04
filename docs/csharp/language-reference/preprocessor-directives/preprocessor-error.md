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
# <a name="error-c-reference"></a><span data-ttu-id="8bd07-103">#error (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8bd07-103">#error (C# Reference)</span></span>

<span data-ttu-id="8bd07-104">`#error` を使用すると、コード内の特定の場所からユーザー定義の [CS1029](../compiler-messages/cs1029.md) エラーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="8bd07-104">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="8bd07-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8bd07-105">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="8bd07-106">コンパイラは `#error version` を特別な方法で処理し、使用されているコンパイラと言語バージョンを含むメッセージと共にコンパイラ エラー CS8304 を報告します。</span><span class="sxs-lookup"><span data-stu-id="8bd07-106">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bd07-107">注釈</span><span class="sxs-lookup"><span data-stu-id="8bd07-107">Remarks</span></span>

<span data-ttu-id="8bd07-108">`#error` は条件付きディレクティブ内で一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bd07-108">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="8bd07-109">[#warning](./preprocessor-warning.md) を使用してユーザー定義の警告を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bd07-109">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="8bd07-110">例</span><span class="sxs-lookup"><span data-stu-id="8bd07-110">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8bd07-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bd07-111">See also</span></span>

- [<span data-ttu-id="8bd07-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="8bd07-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8bd07-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8bd07-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8bd07-114">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="8bd07-114">C# Preprocessor Directives</span></span>](./index.md)

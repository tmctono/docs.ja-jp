---
title: 構造体メンバーとして宣言された配列を初期サイズで宣言することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 83342b780c0fa7c3a2e0a6797b80ef788117ae92
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250151"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="1a413-102">構造体メンバーとして宣言された配列を初期サイズで宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a413-102">Arrays declared as structure members cannot be declared with an initial size</span></span>

<span data-ttu-id="1a413-103">構造体の配列が初期サイズで宣言されています。</span><span class="sxs-lookup"><span data-stu-id="1a413-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="1a413-104">構造体要素を初期化することはできません。また、配列サイズの宣言は初期化の1つの形式です。</span><span class="sxs-lookup"><span data-stu-id="1a413-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>

<span data-ttu-id="1a413-105">**エラー ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="1a413-105">**Error ID:** BC31043</span></span>

## <a name="example"></a><span data-ttu-id="1a413-106">例</span><span class="sxs-lookup"><span data-stu-id="1a413-106">Example</span></span>

<span data-ttu-id="1a413-107">次の例では、BC31043 が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1a413-107">The following example generates BC31043:</span></span>

```vb
Structure DemoStruct
    Public demoArray(9) As Integer
End Structure
```

## <a name="to-correct-this-error"></a><span data-ttu-id="1a413-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1a413-108">To correct this error</span></span>

1. <span data-ttu-id="1a413-109">構造体の配列を動的として定義します (初期サイズはありません)。</span><span class="sxs-lookup"><span data-stu-id="1a413-109">Define the array in your structure as dynamic (no initial size).</span></span>

2. <span data-ttu-id="1a413-110">配列の特定のサイズが必要な場合は、コードの実行時に[ReDim ステートメント](../statements/redim-statement.md)を使用して動的配列を再作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a413-110">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="1a413-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1a413-111">The following example illustrates this:</span></span>
  
    ```vb
    Structure DemoStruct
        Public demoArray() As Integer
    End Structure
    Sub UseStruct()
        Dim struct As DemoStruct  
        ReDim struct.demoArray(9)
        Struct.demoArray(2) = 777
    End Sub  
    ```
  
## <a name="see-also"></a><span data-ttu-id="1a413-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a413-112">See also</span></span>

- [<span data-ttu-id="1a413-113">配列</span><span class="sxs-lookup"><span data-stu-id="1a413-113">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="1a413-114">2 つのオブジェクトが等しいかどうかをテストする方法構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="1a413-114">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)

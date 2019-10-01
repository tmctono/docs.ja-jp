---
title: 構造体メンバーとして宣言された配列を初期サイズで宣言することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: de9d77aa9ea853b6f044e91878044115588ca77c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701245"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="f5333-102">構造体メンバーとして宣言された配列を初期サイズで宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5333-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="f5333-103">構造体の配列が初期サイズで宣言されています。</span><span class="sxs-lookup"><span data-stu-id="f5333-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="f5333-104">構造体要素を初期化することはできません。また、配列サイズの宣言は初期化の1つの形式です。</span><span class="sxs-lookup"><span data-stu-id="f5333-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="f5333-105">**エラー ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="f5333-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5333-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f5333-106">To correct this error</span></span>  
  
1. <span data-ttu-id="f5333-107">構造体の配列を動的として定義します (初期サイズはありません)。</span><span class="sxs-lookup"><span data-stu-id="f5333-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="f5333-108">配列の特定のサイズが必要な場合は、コードの実行時に[ReDim ステートメント](../../../visual-basic/language-reference/statements/redim-statement.md)を使用して動的配列を再作成できます。</span><span class="sxs-lookup"><span data-stu-id="f5333-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="f5333-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f5333-109">The following example illustrates this.</span></span>  
  
    ```vb  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5333-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5333-110">See also</span></span>

- [<span data-ttu-id="f5333-111">配列</span><span class="sxs-lookup"><span data-stu-id="f5333-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="f5333-112">2 つのオブジェクトが等しいかどうかをテストする方法構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="f5333-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)

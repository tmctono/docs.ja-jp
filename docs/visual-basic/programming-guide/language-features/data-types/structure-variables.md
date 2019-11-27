---
title: 構造体の変数
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346305"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="7b64d-102">構造体の変数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b64d-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="7b64d-103">構造体を作成したら、その型としてプロシージャレベルとモジュールレベルの変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="7b64d-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="7b64d-104">たとえば、コンピューターシステムに関する情報を記録する構造体を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b64d-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="7b64d-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7b64d-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="7b64d-106">これで、その型の変数を宣言できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7b64d-106">You can now declare variables of that type.</span></span> <span data-ttu-id="7b64d-107">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="7b64d-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="7b64d-108">クラスとモジュールでは、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用して宣言された構造体は、既定でパブリックアクセスになります。</span><span class="sxs-lookup"><span data-stu-id="7b64d-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="7b64d-109">構造体をプライベートにする場合は、 [private](../../../../visual-basic/language-reference/modifiers/private.md)キーワードを使用して宣言してください。</span><span class="sxs-lookup"><span data-stu-id="7b64d-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="7b64d-110">構造体の値へのアクセス</span><span class="sxs-lookup"><span data-stu-id="7b64d-110">Access to Structure Values</span></span>

<span data-ttu-id="7b64d-111">構造体変数の要素の値を割り当てたり、取得したりするには、オブジェクトのプロパティの設定と取得に使用するのと同じ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b64d-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="7b64d-112">メンバーアクセス演算子 (`.`) は、構造体変数名と要素名の間に配置します。</span><span class="sxs-lookup"><span data-stu-id="7b64d-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="7b64d-113">次の例では、以前に型 `systemInfo`として宣言された変数の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7b64d-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="7b64d-114">構造体変数の割り当て</span><span class="sxs-lookup"><span data-stu-id="7b64d-114">Assigning Structure Variables</span></span>

<span data-ttu-id="7b64d-115">また、両方が同じ構造体型である場合は、1つの変数を別の変数に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b64d-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="7b64d-116">これにより、1つの構造体のすべての要素が、他方の内の対応する要素にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7b64d-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="7b64d-117">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="7b64d-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="7b64d-118">構造体要素が `String`、`Object`、配列などの参照型である場合、データへのポインターがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7b64d-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="7b64d-119">前の例では、`systemInfo` にオブジェクト変数が含まれていた場合、前の例ではポインターが `mySystem` から `yourSystem`にコピーされています。また、1つの構造体を介してオブジェクトのデータを変更すると、他の構造体を使用してアクセスしたときに有効になります。</span><span class="sxs-lookup"><span data-stu-id="7b64d-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b64d-120">参照</span><span class="sxs-lookup"><span data-stu-id="7b64d-120">See also</span></span>

- [<span data-ttu-id="7b64d-121">データの種類</span><span class="sxs-lookup"><span data-stu-id="7b64d-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="7b64d-122">基本データ型</span><span class="sxs-lookup"><span data-stu-id="7b64d-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="7b64d-123">複合データ型</span><span class="sxs-lookup"><span data-stu-id="7b64d-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="7b64d-124">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="7b64d-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="7b64d-125">構造体</span><span class="sxs-lookup"><span data-stu-id="7b64d-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="7b64d-126">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="7b64d-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="7b64d-127">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="7b64d-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="7b64d-128">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="7b64d-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="7b64d-129">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="7b64d-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="7b64d-130">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b64d-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)

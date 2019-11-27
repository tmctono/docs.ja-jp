---
title: 構造体とその他のプログラミング要素
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 309d0e5214897675e1758bd98b964392b379ca1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346120"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="febef-102">構造体およびその他のプログラミング要素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="febef-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="febef-103">構造体は、配列、オブジェクト、およびプロシージャと組み合わせて使用することも、相互に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="febef-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="febef-104">相互作用は、これらの要素が個別に使用するのと同じ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="febef-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="febef-105">構造体の宣言で構造体の要素を初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="febef-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="febef-106">値は、構造体型として宣言されている変数の要素にのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="febef-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="febef-107">構造体と配列</span><span class="sxs-lookup"><span data-stu-id="febef-107">Structures and Arrays</span></span>  
 <span data-ttu-id="febef-108">構造体には、配列を1つ以上の要素として含めることができます。</span><span class="sxs-lookup"><span data-stu-id="febef-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="febef-109">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="febef-110">構造体内の配列の値には、オブジェクトのプロパティにアクセスするのと同じ方法でアクセスします。</span><span class="sxs-lookup"><span data-stu-id="febef-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="febef-111">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="febef-112">構造体の配列を宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="febef-112">You can also declare an array of structures.</span></span> <span data-ttu-id="febef-113">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="febef-114">このデータアーキテクチャのコンポーネントにアクセスするには、同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="febef-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="febef-115">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="febef-116">構造体とオブジェクト</span><span class="sxs-lookup"><span data-stu-id="febef-116">Structures and Objects</span></span>  
 <span data-ttu-id="febef-117">構造体には、オブジェクトを1つ以上の要素として含めることができます。</span><span class="sxs-lookup"><span data-stu-id="febef-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="febef-118">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="febef-119">`Object`ではなく、このような宣言では特定のオブジェクトクラスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="febef-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="febef-120">構造体とプロシージャ</span><span class="sxs-lookup"><span data-stu-id="febef-120">Structures and Procedures</span></span>  
 <span data-ttu-id="febef-121">プロシージャ引数として構造体を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="febef-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="febef-122">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="febef-123">前の例では、*参照によって*構造体を渡しています。これにより、プロシージャは、呼び出し元のコードで変更が有効になるように要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="febef-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="febef-124">このような変更に対して構造体を保護する場合は、値で渡します。</span><span class="sxs-lookup"><span data-stu-id="febef-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="febef-125">`Function` プロシージャから構造体を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="febef-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="febef-126">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-126">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a><span data-ttu-id="febef-127">構造体内の構造体</span><span class="sxs-lookup"><span data-stu-id="febef-127">Structures Within Structures</span></span>  
 <span data-ttu-id="febef-128">構造体には他の構造体を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="febef-128">Structures can contain other structures.</span></span> <span data-ttu-id="febef-129">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="febef-129">The following example illustrates this.</span></span>  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 <span data-ttu-id="febef-130">また、この方法を使用して、あるモジュールで定義されている構造体を、別のモジュールで定義されている構造体内にカプセル化することもできます。</span><span class="sxs-lookup"><span data-stu-id="febef-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="febef-131">構造体には、任意の深さの他の構造体を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="febef-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febef-132">参照</span><span class="sxs-lookup"><span data-stu-id="febef-132">See also</span></span>

- [<span data-ttu-id="febef-133">データの種類</span><span class="sxs-lookup"><span data-stu-id="febef-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="febef-134">基本データ型</span><span class="sxs-lookup"><span data-stu-id="febef-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="febef-135">複合データ型</span><span class="sxs-lookup"><span data-stu-id="febef-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="febef-136">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="febef-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="febef-137">構造体</span><span class="sxs-lookup"><span data-stu-id="febef-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="febef-138">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="febef-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="febef-139">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="febef-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="febef-140">構造体変数</span><span class="sxs-lookup"><span data-stu-id="febef-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="febef-141">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="febef-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="febef-142">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="febef-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)

---
title: Implements ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 865e99aa0e27591d10fde1465047a2e6bf183bbf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581785"
---
# <a name="implements-statement"></a><span data-ttu-id="f5fe2-102">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="f5fe2-102">Implements Statement</span></span>
<span data-ttu-id="f5fe2-103">表示されるクラスまたは構造体の定義に実装する必要がある1つ以上のインターフェイス、またはインターフェイスメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5fe2-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5fe2-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="f5fe2-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f5fe2-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="f5fe2-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-106">Required.</span></span> <span data-ttu-id="f5fe2-107">クラスまたは構造体の対応するメンバーによって実装されるプロパティ、プロシージャ、およびイベントを持つインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="f5fe2-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-108">Required.</span></span> <span data-ttu-id="f5fe2-109">実装されているインターフェイスのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5fe2-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5fe2-110">Remarks</span></span>  
 <span data-ttu-id="f5fe2-111">インターフェイスは、インターフェイスによってカプセル化されるメンバー (プロパティ、プロシージャ、およびイベント) を表すプロトタイプのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="f5fe2-112">インターフェイスには、メンバーの宣言のみが含まれます。クラスと構造体は、これらのメンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="f5fe2-113">詳細については、「[インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="f5fe2-114">@No__t_0 ステートメントは、`Class` または `Structure` ステートメントの直後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="f5fe2-115">インターフェイスを実装する場合は、インターフェイスで宣言されたすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="f5fe2-116">メンバーを省略すると、構文エラーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="f5fe2-117">個々のメンバーを実装するには、クラスまたは構造体でメンバーを宣言するときに、 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)キーワード (`Implements` ステートメントとは別のもの) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="f5fe2-118">詳細については、「[インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="f5fe2-119">クラスでは、プロパティとプロシージャの[プライベート](../../../visual-basic/language-reference/modifiers/private.md)実装を使用できますが、これらのメンバーには、インターフェイスの型として宣言された変数に、実装するクラスのインスタンスをキャストすることによってのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5fe2-120">例</span><span class="sxs-lookup"><span data-stu-id="f5fe2-120">Example</span></span>  
 <span data-ttu-id="f5fe2-121">次の例は、`Implements` ステートメントを使用してインターフェイスのメンバーを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="f5fe2-122">これは、イベント、プロパティ、およびプロシージャを使用して `ICustomerInfo` という名前のインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="f5fe2-123">クラス `customerInfo`、インターフェイスで定義されているすべてのメンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="f5fe2-124">クラス `customerInfo` は、クラスが `ICustomerInfo` インターフェイスのすべてのメンバーを実装していることを示すために、別のソースコード行で `Implements` ステートメントを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="f5fe2-125">次に、クラスの各メンバーは、メンバー宣言の一部として `Implements` キーワードを使用して、そのインターフェイスメンバーを実装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5fe2-126">例</span><span class="sxs-lookup"><span data-stu-id="f5fe2-126">Example</span></span>  
 <span data-ttu-id="f5fe2-127">次の2つの手順は、前の例で実装されたインターフェイスを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="f5fe2-128">実装をテストするには、これらのプロシージャをプロジェクトに追加し、`testImplements` プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5fe2-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="f5fe2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5fe2-129">See also</span></span>

- [<span data-ttu-id="f5fe2-130">Sub New</span><span class="sxs-lookup"><span data-stu-id="f5fe2-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="f5fe2-131">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="f5fe2-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="f5fe2-132">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5fe2-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

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
ms.openlocfilehash: 1f0c6b052ead303e0b43465dac2067422abc4ef8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818872"
---
# <a name="implements-statement"></a><span data-ttu-id="3f9d0-102">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="3f9d0-102">Implements Statement</span></span>
<span data-ttu-id="3f9d0-103">1 つ以上のインターフェイス、またはインターフェイス メンバーの場合、クラスで実装する必要がありますまたはが表示される構造体の定義を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f9d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f9d0-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="3f9d0-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="3f9d0-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="3f9d0-106">必須。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-106">Required.</span></span> <span data-ttu-id="3f9d0-107">プロパティ、プロシージャ、およびイベントのクラスまたは構造体に対応するメンバーを実装するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="3f9d0-108">必須。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-108">Required.</span></span> <span data-ttu-id="3f9d0-109">実装されているインターフェイスのメンバー。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f9d0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f9d0-110">Remarks</span></span>  
 <span data-ttu-id="3f9d0-111">インターフェイスは、コレクション メンバー (プロパティ、プロシージャ、およびイベント) を表すプロトタイプのインターフェイスをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="3f9d0-112">インターフェイスにメンバーの宣言のみを含めるクラスと構造体は、これらのメンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="3f9d0-113">詳細については、「[インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="3f9d0-114">`Implements`ステートメントの直後にする必要があります、`Class`または`Structure`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="3f9d0-115">インターフェイスを実装する場合は、インターフェイスで宣言されているすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="3f9d0-116">任意のメンバーを省略すると、構文エラーであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="3f9d0-117">指定した個々 のメンバーを実装するために、[実装](../../../visual-basic/language-reference/statements/implements-clause.md)キーワード (これとは別、`Implements`ステートメント) クラスまたは構造体のメンバーを宣言する場合。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="3f9d0-118">詳細については、「[インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="3f9d0-119">クラスを使用する[プライベート](../../../visual-basic/language-reference/modifiers/private.md)プロパティと手順については、これらのメンバーの実装は、インターフェイスの型の変数に実装するクラスのインスタンスが宣言されているキャストによってのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f9d0-120">例</span><span class="sxs-lookup"><span data-stu-id="3f9d0-120">Example</span></span>  
 <span data-ttu-id="3f9d0-121">次の例は、使用する方法を示します、`Implements`インターフェイスのメンバーを実装するステートメント。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="3f9d0-122">という名前のインターフェイスを定義`ICustomerInfo`イベント、プロパティ、およびプロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="3f9d0-123">クラスは、`customerInfo`インターフェイスで定義されているすべてのメンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="3f9d0-124">なお、クラス`customerInfo`を使用して、`Implements`クラスのすべてのメンバーを実装することを示す別のソース コード行のステートメントで、`ICustomerInfo`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="3f9d0-125">クラス内の各メンバーを使用して、`Implements`をそのインターフェイスのメンバーを実装することを示すために、メンバー宣言の一部としてキーワード。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f9d0-126">例</span><span class="sxs-lookup"><span data-stu-id="3f9d0-126">Example</span></span>  
 <span data-ttu-id="3f9d0-127">次の 2 つの手順では、前の例で実装されたインターフェイスを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="3f9d0-128">実装をテストするには、呼び出しをプロジェクトにこれらの手順を追加、`testImplements`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="3f9d0-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="3f9d0-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f9d0-129">See also</span></span>

- [<span data-ttu-id="3f9d0-130">Implements</span><span class="sxs-lookup"><span data-stu-id="3f9d0-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="3f9d0-131">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="3f9d0-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="3f9d0-132">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f9d0-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

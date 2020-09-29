---
title: Implements ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: b982057d2094f807b68d5190dfad388fb9a2c65a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873231"
---
# <a name="implements-statement"></a><span data-ttu-id="eca1c-102">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="eca1c-102">Implements Statement</span></span>

<span data-ttu-id="eca1c-103">それが存在するクラスまたは構造体の定義に、実装する必要のある 1 つ以上のインターフェイス、つまりインターフェイス メンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="eca1c-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="eca1c-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="eca1c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="eca1c-105">Parts</span></span>  

 `interfacename`  
 <span data-ttu-id="eca1c-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="eca1c-106">Required.</span></span> <span data-ttu-id="eca1c-107">クラスまたは構造体に、対応するメンバーによって実装されるプロパティ、プロシージャ、およびイベントを持つインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eca1c-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="eca1c-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="eca1c-108">Required.</span></span> <span data-ttu-id="eca1c-109">実装されるインターフェイスのメンバー。</span><span class="sxs-lookup"><span data-stu-id="eca1c-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eca1c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="eca1c-110">Remarks</span></span>  

 <span data-ttu-id="eca1c-111">インターフェイスは、インターフェイスによってカプセル化されるメンバー (プロパティ、プロシージャ、およびイベント) を表すプロトタイプのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="eca1c-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="eca1c-112">インターフェイスには、メンバーの宣言のみが含まれます。クラスと構造体で、これらのメンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="eca1c-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="eca1c-113">詳細については、「[インターフェイス](../../programming-guide/language-features/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eca1c-113">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="eca1c-114">`Implements` ステートメントは、`Class` または `Structure` ステートメントの直後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eca1c-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="eca1c-115">インターフェイスを実装する場合は、インターフェイスで宣言されたすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eca1c-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="eca1c-116">メンバーを省略すると、構文エラーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="eca1c-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="eca1c-117">個々のメンバーを実装するには、クラスまたは構造体でメンバーを宣言するときに、[Implements](implements-clause.md) キーワード (`Implements` ステートメントとは別) を指定します。</span><span class="sxs-lookup"><span data-stu-id="eca1c-117">To implement an individual member, you specify the [Implements](implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="eca1c-118">詳細については、「[インターフェイス](../../programming-guide/language-features/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eca1c-118">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="eca1c-119">クラスでは、プロパティとプロシージャの [Private](../modifiers/private.md) 実装を使用できますが、インターフェイスの型として宣言された変数に、実装するクラスのインスタンスをキャストすることによってのみ、これらのメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eca1c-119">Classes can use [Private](../modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eca1c-120">例</span><span class="sxs-lookup"><span data-stu-id="eca1c-120">Example</span></span>  

 <span data-ttu-id="eca1c-121">次の例は、`Implements` ステートメントを使用して、インターフェイスのメンバーを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="eca1c-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="eca1c-122">これは、イベント、プロパティ、およびプロシージャを含む `ICustomerInfo` という名前のインターフェイスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="eca1c-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="eca1c-123">クラス `customerInfo` では、インターフェイスで定義されているすべてのメンバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="eca1c-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="eca1c-124">クラス `customerInfo` では、別のソース コード行で `Implements` ステートメントを使用して、クラスで `ICustomerInfo` インターフェイスのすべてのメンバーを実装していることを示していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eca1c-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="eca1c-125">次に、クラスの各メンバーで、そのメンバー宣言の一部として `Implements` キーワードを使用して、そのインターフェイス　メンバーを実装していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="eca1c-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eca1c-126">例</span><span class="sxs-lookup"><span data-stu-id="eca1c-126">Example</span></span>  

 <span data-ttu-id="eca1c-127">次の 2 つのプロシージャでは、前の例で実装したインターフェイスを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="eca1c-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="eca1c-128">実装をテストするには、これらのプロシージャをプロジェクトに追加し、`testImplements` プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eca1c-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="eca1c-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="eca1c-129">See also</span></span>

- [<span data-ttu-id="eca1c-130">Implements</span><span class="sxs-lookup"><span data-stu-id="eca1c-130">Implements</span></span>](implements-clause.md)
- [<span data-ttu-id="eca1c-131">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="eca1c-131">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="eca1c-132">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eca1c-132">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)

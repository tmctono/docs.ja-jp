---
title: '方法 : 変数の可用性を制御する'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 886b57909cf6ba25dbaceea5c5f06eb4e3ba6f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345390"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="4e319-102">方法: 変数の可用性を制御する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e319-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="4e319-103">変数の可用性を制御するには、*アクセスレベル*を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e319-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="4e319-104">アクセスレベルによって、変数に対する読み取りまたは書き込みのアクセス許可を持つコードが決まります。</span><span class="sxs-lookup"><span data-stu-id="4e319-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="4e319-105">*メンバー変数*(モジュールレベルおよびプロシージャ外で定義されます) は、既定でパブリックアクセスになります。これは、参照できるすべてのコードがアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4e319-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="4e319-106">これは、アクセス修飾子を指定することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="4e319-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="4e319-107">*ローカル変数*(プロシージャ内で定義) とにはパブリックアクセスがありますが、そのプロシージャ内のコードだけがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4e319-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="4e319-108">ローカル変数のアクセスレベルを変更することはできませんが、それを含むプロシージャのアクセスレベルを変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="4e319-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="4e319-109">詳細については、「[Visual Basic でのアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e319-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="4e319-110">プライベートアクセスとパブリックアクセス</span><span class="sxs-lookup"><span data-stu-id="4e319-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="4e319-111">モジュール、クラス、または構造体内からのみ変数にアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="4e319-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="4e319-112">変数の[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)をモジュール、クラス、または構造体の内部に配置しますが、プロシージャの外側に配置します。</span><span class="sxs-lookup"><span data-stu-id="4e319-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4e319-113">`Dim` ステートメントに[Private](../../../../visual-basic/language-reference/modifiers/private.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="4e319-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4e319-114">モジュール、クラス、または構造体内のどこからでも変数の読み取りまたは書き込みを行うことができますが、外部からは読み取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="4e319-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="4e319-115">参照可能なコードから変数にアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="4e319-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="4e319-116">メンバー変数の場合は、変数の `Dim` ステートメントをモジュール、クラス、または構造体の内部に配置しますが、プロシージャの外側に配置します。</span><span class="sxs-lookup"><span data-stu-id="4e319-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4e319-117">`Dim` ステートメントに[Public](../../../../visual-basic/language-reference/modifiers/public.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="4e319-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4e319-118">アセンブリと相互運用できる任意のコードから変数の読み取りまたは書き込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e319-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="4e319-119">または</span><span class="sxs-lookup"><span data-stu-id="4e319-119">-or-</span></span>  
  
1. <span data-ttu-id="4e319-120">ローカル変数の場合は、プロシージャ内に変数の `Dim` ステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="4e319-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="4e319-121">`Dim` ステートメントに `Public` キーワードを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="4e319-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4e319-122">変数の読み取りまたは書き込みは、プロシージャ内の任意の場所から行うことができますが、外部からは実行できません。</span><span class="sxs-lookup"><span data-stu-id="4e319-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="4e319-123">保護されたアクセスとフレンドアクセス</span><span class="sxs-lookup"><span data-stu-id="4e319-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="4e319-124">変数のアクセスレベルは、そのクラス、派生クラス、またはそのアセンブリに限定できます。</span><span class="sxs-lookup"><span data-stu-id="4e319-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="4e319-125">また、これらの制限の和集合を指定することもできます。これにより、任意の派生クラスまたは同じアセンブリ内の他の場所のコードからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e319-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="4e319-126">この共用体を指定するには、同じ宣言で `Protected` キーワードと `Friend` キーワードを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="4e319-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="4e319-127">クラスと派生クラス内からのみ変数にアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="4e319-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="4e319-128">変数の `Dim` ステートメントをクラス内に配置しますが、プロシージャの外側に配置します。</span><span class="sxs-lookup"><span data-stu-id="4e319-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4e319-129">`Dim` ステートメントに[Protected](../../../../visual-basic/language-reference/modifiers/protected.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="4e319-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4e319-130">変数の読み取りまたは書き込みは、クラス内の任意の場所から行うことができます。また、派生チェーン内のクラスの外部から派生したクラスから派生することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e319-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="4e319-131">同じアセンブリ内からのみ変数にアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="4e319-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="4e319-132">変数の `Dim` ステートメントをモジュール、クラス、または構造体の内部に配置しますが、プロシージャの外側に配置します。</span><span class="sxs-lookup"><span data-stu-id="4e319-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="4e319-133">`Dim` ステートメントに[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="4e319-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4e319-134">モジュール、クラス、または構造体内の任意の場所から、また同じアセンブリ内の任意のコードから、変数に対する読み取りまたは書き込みを行うことができます。ただし、アセンブリの外部からは参照できません。</span><span class="sxs-lookup"><span data-stu-id="4e319-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e319-135">例</span><span class="sxs-lookup"><span data-stu-id="4e319-135">Example</span></span>  
 <span data-ttu-id="4e319-136">次の例では、`Public`、`Protected`、`Friend`、`Protected Friend`、および `Private` アクセスレベルを持つ変数の宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="4e319-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="4e319-137">`Dim` ステートメントでアクセスレベルを指定する場合は、`Dim` キーワードを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4e319-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="4e319-138">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4e319-138">.NET Framework Security</span></span>  
 <span data-ttu-id="4e319-139">変数のアクセスレベルが制限されているほど、悪意のあるコードによって不適切に使用される可能性が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="4e319-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e319-140">参照</span><span class="sxs-lookup"><span data-stu-id="4e319-140">See also</span></span>

- [<span data-ttu-id="4e319-141">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="4e319-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="4e319-142">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e319-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="4e319-143">Public</span><span class="sxs-lookup"><span data-stu-id="4e319-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="4e319-144">Protected</span><span class="sxs-lookup"><span data-stu-id="4e319-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="4e319-145">Friend</span><span class="sxs-lookup"><span data-stu-id="4e319-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="4e319-146">Private</span><span class="sxs-lookup"><span data-stu-id="4e319-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)

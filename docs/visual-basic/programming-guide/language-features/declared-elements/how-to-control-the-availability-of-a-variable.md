---
title: '方法: 変数 (Visual Basic) の可用性を制御します。'
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
ms.openlocfilehash: 419f3eed30a5d4b35bcb9dde5242b9092ee9cb79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610500"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="581a3-102">方法: 変数 (Visual Basic) の可用性を制御します。</span><span class="sxs-lookup"><span data-stu-id="581a3-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="581a3-103">指定することで、変数の可用性を制御するその*アクセス レベル*します。</span><span class="sxs-lookup"><span data-stu-id="581a3-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="581a3-104">どのようなコードは、変数に対する読み取りまたは書き込み権限を持つアクセス レベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="581a3-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="581a3-105">*メンバー変数*(モジュール レベルで、プロシージャの外に定義された) 既定でパブリック アクセスは、表示できるすべてのコードがアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="581a3-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="581a3-106">これは、アクセス修飾子を指定することで変更できます。</span><span class="sxs-lookup"><span data-stu-id="581a3-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="581a3-107">*ローカル変数*(プロシージャの内部で定義されている)、プロシージャ内のコードだけがアクセスできますが、パブリック アクセスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="581a3-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="581a3-108">ローカル変数のアクセス レベルを変更することはできませんが、それを含むプロシージャのアクセス レベルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="581a3-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="581a3-109">詳細については、[ Visual Basic のアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581a3-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="581a3-110">プライベートおよびパブリックのアクセス</span><span class="sxs-lookup"><span data-stu-id="581a3-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="581a3-111">変数をそのモジュール、クラスまたは構造内からのみアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="581a3-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="581a3-112">場所、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)モジュール、クラス、または構造体の内部では、プロシージャの外部の変数。</span><span class="sxs-lookup"><span data-stu-id="581a3-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="581a3-113">含める、[プライベート](../../../../visual-basic/language-reference/modifiers/private.md)キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="581a3-114">読み取りまたはからではなくが、モジュール、クラス、または構造内で任意の場所から変数への書き込みができる外です。</span><span class="sxs-lookup"><span data-stu-id="581a3-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="581a3-115">変数を参照できる任意のコードからアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="581a3-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="581a3-116">メンバー変数では、配置、`Dim`変数ではなく、プロシージャの外部モジュール、クラス、または構造体には、内部のステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="581a3-117">含める、[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="581a3-118">読み取りまたはアセンブリと同時に使用する任意のコードから、変数に書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="581a3-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="581a3-119">- または -</span><span class="sxs-lookup"><span data-stu-id="581a3-119">-or-</span></span>  
  
1. <span data-ttu-id="581a3-120">ローカル変数では、配置、`Dim`プロシージャ内にある変数のステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="581a3-121">含めないでください、`Public`キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="581a3-122">読み取りまたはからは、プロシージャ内で任意の場所から変数への書き込みができる外です。</span><span class="sxs-lookup"><span data-stu-id="581a3-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="581a3-123">保護されているとフレンド アクセス</span><span class="sxs-lookup"><span data-stu-id="581a3-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="581a3-124">変数をクラスおよび派生クラス、またはそのアセンブリへのアクセス レベルを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="581a3-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="581a3-125">同じアセンブリ内の他の場所または任意の派生クラスでは、コードからアクセスを許可するこれらの制限の和集合を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="581a3-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="581a3-126">結合することでこの和集合を指定する、`Protected`と`Friend`同じ宣言内のキーワード。</span><span class="sxs-lookup"><span data-stu-id="581a3-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="581a3-127">変数をそのクラスと派生クラス内からのみアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="581a3-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="581a3-128">場所、`Dim`変数、クラス内では、プロシージャの外側のステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="581a3-129">含める、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="581a3-130">読み取りまたはからではなくが、それから派生したあらゆるクラス内からだけでなく、クラス内で任意の場所から変数への書き込みができる派生チェーン内のクラス外です。</span><span class="sxs-lookup"><span data-stu-id="581a3-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="581a3-131">変数を同じアセンブリ内からのみアクセスできるようにするには</span><span class="sxs-lookup"><span data-stu-id="581a3-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="581a3-132">場所、`Dim`変数ではなく、プロシージャの外部モジュール、クラス、または構造体には、内部のステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="581a3-133">含める、[フレンド](../../../../visual-basic/language-reference/modifiers/friend.md)キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="581a3-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="581a3-134">読み取りまたは、モジュール、クラス、または構造内で任意の場所だけでなく、コードからは、同じアセンブリ内から変数への書き込みができるアセンブリの外側です。</span><span class="sxs-lookup"><span data-stu-id="581a3-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="581a3-135">例</span><span class="sxs-lookup"><span data-stu-id="581a3-135">Example</span></span>  
 <span data-ttu-id="581a3-136">次の例では、変数の宣言`Public`、 `Protected`、 `Friend`、 `Protected Friend`、および`Private`アクセス レベル。</span><span class="sxs-lookup"><span data-stu-id="581a3-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="581a3-137">その場合、`Dim`ステートメントが、アクセス レベルを指定しますを含める必要はありません、`Dim`キーワード。</span><span class="sxs-lookup"><span data-stu-id="581a3-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="581a3-138">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="581a3-138">.NET Framework Security</span></span>  
 <span data-ttu-id="581a3-139">制限の厳しいアクセス レベルで変数をその悪意のあるコードが不正に、小さい方の可能性を使用して、します。</span><span class="sxs-lookup"><span data-stu-id="581a3-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="581a3-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="581a3-140">See also</span></span>

- [<span data-ttu-id="581a3-141">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="581a3-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="581a3-142">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="581a3-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="581a3-143">Public</span><span class="sxs-lookup"><span data-stu-id="581a3-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="581a3-144">Protected</span><span class="sxs-lookup"><span data-stu-id="581a3-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="581a3-145">Friend</span><span class="sxs-lookup"><span data-stu-id="581a3-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="581a3-146">Private</span><span class="sxs-lookup"><span data-stu-id="581a3-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)

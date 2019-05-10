---
title: アクセスするインスタンスがインターフェイス型であるため、遅延バインドされたオーバーロードの解決は '<procedurename>' に適用されません。
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 8ceff80842ec4e7364a55578c1c3fdb870c73ece
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661964"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="edb9a-102">遅延バインドされたオーバー ロードの解決には適用できません '\<procedurename >' へのアクセスのインスタンスがインターフェイス型であるため</span><span class="sxs-lookup"><span data-stu-id="edb9a-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>
<span data-ttu-id="edb9a-103">オーバー ロードされたプロパティまたはプロシージャへの参照を解決するのには、コンパイラがしようとしていますが、型の引数であるため、参照が失敗した`Object`インターフェイスのデータ型であり、参照元オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="edb9a-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="edb9a-104">`Object`引数は、遅延バインディングとして参照を解決するのには、コンパイラを強制します。</span><span class="sxs-lookup"><span data-stu-id="edb9a-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="edb9a-105">このような場合は、コンパイラを基になるインターフェイスを実装するクラスの代わりにオーバー ロードを解決します。</span><span class="sxs-lookup"><span data-stu-id="edb9a-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="edb9a-106">クラスには、オーバー ロードされたバージョンのいずれかが名前変更、コンパイラはその名前が異なるため、オーバー ロードするには、そのバージョンを考慮しません。</span><span class="sxs-lookup"><span data-stu-id="edb9a-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="edb9a-107">これで、コンパイラは参照を解決するのには、適切な選択されている可能性があるときに名前を変更したバージョンを無視します。</span><span class="sxs-lookup"><span data-stu-id="edb9a-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="edb9a-108">**エラー ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="edb9a-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="edb9a-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="edb9a-109">To correct this error</span></span>  
  
- <span data-ttu-id="edb9a-110">使用`CType`から引数をキャストする`Object`呼び出そうとするオーバー ロードのシグネチャで指定された型にします。</span><span class="sxs-lookup"><span data-stu-id="edb9a-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="edb9a-111">基になるインターフェイスを参照しているオブジェクトをキャストする役立ちませんに注意してください。</span><span class="sxs-lookup"><span data-stu-id="edb9a-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="edb9a-112">このエラーを回避するために引数をキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="edb9a-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edb9a-113">例</span><span class="sxs-lookup"><span data-stu-id="edb9a-113">Example</span></span>  
 <span data-ttu-id="edb9a-114">次の例は、オーバー ロードされた呼び出し`Sub`コンパイル時にこのエラーが発生するプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="edb9a-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 <span data-ttu-id="edb9a-115">コンパイラへの呼び出しを許可されている場合、前の例で`s1`が書き込まれると、解決が行わクラスを通じて`c1`インターフェイスではなく`i1`します。</span><span class="sxs-lookup"><span data-stu-id="edb9a-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="edb9a-116">つまり、コンパイラは見なしません`s2`その名前が異なるため、`c1`は適切な選択であるで定義されている場合でも、`i1`します。</span><span class="sxs-lookup"><span data-stu-id="edb9a-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="edb9a-117">次のコード行のいずれかへの呼び出しを変更することで、エラーを修正できます。</span><span class="sxs-lookup"><span data-stu-id="edb9a-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="edb9a-118">前の行のコードに明示的にキャスト、`Object`変数`o1`オーバー ロードは、定義されているパラメーターの型のいずれかにします。</span><span class="sxs-lookup"><span data-stu-id="edb9a-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb9a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="edb9a-119">See also</span></span>

- [<span data-ttu-id="edb9a-120">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="edb9a-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="edb9a-121">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="edb9a-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="edb9a-122">CType 関数</span><span class="sxs-lookup"><span data-stu-id="edb9a-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)

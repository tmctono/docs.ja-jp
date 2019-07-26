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
ms.openlocfilehash: 1fe3c4a29b542302b3615459142a3c565aa8244f
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513026"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="7220a-102">アクセスするインスタンスがインターフェイス型である\<ため、遅延バインディングされたオーバーロードの解決は ' procedurename > ' に適用できません</span><span class="sxs-lookup"><span data-stu-id="7220a-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="7220a-103">コンパイラは、オーバーロードされたプロパティまたはプロシージャへの参照を解決しようとしていますが、引数`Object`が型であり、参照元のオブジェクトがインターフェイスのデータ型を持っているため、参照は失敗します。</span><span class="sxs-lookup"><span data-stu-id="7220a-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="7220a-104">引数`Object`は、コンパイラが参照を遅延バインディングとして解決することを強制します。</span><span class="sxs-lookup"><span data-stu-id="7220a-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="7220a-105">このような場合、コンパイラは、基になるインターフェイスを使用するのではなく、実装するクラスを使用してオーバーロードを解決します。</span><span class="sxs-lookup"><span data-stu-id="7220a-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="7220a-106">クラスがオーバーロードされたバージョンの1つの名前を変更した場合、コンパイラはそのバージョンの名前が異なるため、そのバージョンがオーバーロードであるとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="7220a-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="7220a-107">これにより、コンパイラは、参照を解決するための正しい選択が行われている可能性がある場合に、名前が変更されたバージョンを無視します。</span><span class="sxs-lookup"><span data-stu-id="7220a-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="7220a-108">**エラー ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="7220a-108">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7220a-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="7220a-109">To correct this error</span></span>

- <span data-ttu-id="7220a-110">引数`CType`をから`Object`呼び出すオーバーロードのシグネチャで指定された型にキャストするには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="7220a-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="7220a-111">参照元のオブジェクトを基になるインターフェイスにキャストすることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7220a-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="7220a-112">このエラーを回避するには、引数をキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7220a-112">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="7220a-113">例</span><span class="sxs-lookup"><span data-stu-id="7220a-113">Example</span></span>

<span data-ttu-id="7220a-114">次の例は、コンパイル時にこの`Sub`エラーを発生させるオーバーロードされたプロシージャの呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="7220a-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

```vb
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

<span data-ttu-id="7220a-115">前の例では、コンパイラがの呼び出しを`s1`書き込み済みとして許可した場合、インターフェイス`i1`で`c1`はなくクラスを使用して解決が行われます。</span><span class="sxs-lookup"><span data-stu-id="7220a-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="7220a-116">これは、で定義されている`s2` `i1`正しい選択であっても`c1`、コンパイラではその名前が異なるために考慮されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7220a-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="7220a-117">このエラーを修正するには、次のいずれかのコード行の呼び出しを変更します。</span><span class="sxs-lookup"><span data-stu-id="7220a-117">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="7220a-118">前のコード行では、オーバーロードに対し`Object`て`o1`定義されているいずれかのパラメーター型に変数を明示的にキャストします。</span><span class="sxs-lookup"><span data-stu-id="7220a-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="7220a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7220a-119">See also</span></span>

- [<span data-ttu-id="7220a-120">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="7220a-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="7220a-121">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="7220a-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="7220a-122">CType 関数</span><span class="sxs-lookup"><span data-stu-id="7220a-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)

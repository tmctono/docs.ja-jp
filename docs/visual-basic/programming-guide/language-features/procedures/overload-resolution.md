---
title: オーバーロードの解決
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 0e69136b1e3015055cad9852bf04151f57558b88
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352646"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="c9bd7-102">オーバーロードの解決法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9bd7-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="c9bd7-103">オーバーロードされたいくつかのバージョンで定義されているプロシージャへの呼び出しが Visual Basic コンパイラによって検出されると、コンパイラは呼び出すオーバーロードを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="c9bd7-104">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="c9bd7-105">**アクセシビリティ。**</span><span class="sxs-lookup"><span data-stu-id="c9bd7-105">**Accessibility.**</span></span> <span data-ttu-id="c9bd7-106">これにより、呼び出し元のコードが呼び出しを妨げるアクセスレベルのオーバーロードが排除されます。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="c9bd7-107">**パラメーターの数。**</span><span class="sxs-lookup"><span data-stu-id="c9bd7-107">**Number of Parameters.**</span></span> <span data-ttu-id="c9bd7-108">これにより、呼び出しで指定された数よりも多くのパラメーターを定義するオーバーロードが不要になります。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="c9bd7-109">**パラメーターのデータ型。**</span><span class="sxs-lookup"><span data-stu-id="c9bd7-109">**Parameter Data Types.**</span></span> <span data-ttu-id="c9bd7-110">コンパイラは、拡張メソッドよりもインスタンスメソッドを優先します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="c9bd7-111">プロシージャ呼び出しに一致するために拡大変換のみを必要とするインスタンスメソッドが見つかった場合は、すべての拡張メソッドが削除され、コンパイラはインスタンスメソッドの候補だけを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="c9bd7-112">このようなインスタンスメソッドが見つからない場合は、インスタンスメソッドと拡張メソッドの両方で続行されます。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="c9bd7-113">このステップでは、呼び出し元の引数のデータ型をオーバーロードで定義されているパラメーター型に変換できないすべてのオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="c9bd7-114">**縮小変換。**</span><span class="sxs-lookup"><span data-stu-id="c9bd7-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="c9bd7-115">これにより、呼び出し元の引数の型から定義済みのパラメーターの型への縮小変換を必要とするすべてのオーバーロードが排除されます。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="c9bd7-116">これは、型チェックスイッチ ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) が `On` か `Off`かにかかわらず、true になります。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="c9bd7-117">**最小の拡大。**</span><span class="sxs-lookup"><span data-stu-id="c9bd7-117">**Least Widening.**</span></span> <span data-ttu-id="c9bd7-118">コンパイラは、残りのオーバーロードをペアで考慮します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="c9bd7-119">各ペアについて、定義されたパラメーターのデータ型を比較します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="c9bd7-120">オーバーロードのいずれかの型が、他のオーバーロード内の対応する型に拡大変換されると、コンパイラは後者を除外します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="c9bd7-121">つまり、拡大率が最も低いオーバーロードを保持します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="c9bd7-122">**1つの候補です。**</span><span class="sxs-lookup"><span data-stu-id="c9bd7-122">**Single Candidate.**</span></span> <span data-ttu-id="c9bd7-123">オーバーロードを1つだけ保持し、そのオーバーロードの呼び出しを解決するまで、ペアのオーバーロードを検討し続けます。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="c9bd7-124">コンパイラがオーバーロードを1つの候補に減らすことができない場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="c9bd7-125">次の図は、一連のオーバーロードされたバージョンを呼び出すプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="c9bd7-126">![オーバーロードの解決プロセスのフロー図](./media/overload-resolution/determine-overloaded-version.gif "オーバーロードされたバージョン間の解決")</span><span class="sxs-lookup"><span data-stu-id="c9bd7-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>    
  
 <span data-ttu-id="c9bd7-127">次の例は、このオーバーロードの解決プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="c9bd7-128">最初の呼び出しでは、最初の引数の型 (`Short`) が対応するパラメーター (`Byte`) の型に限定されるため、コンパイラは最初のオーバーロードを削除します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="c9bd7-129">次に、2番目のオーバーロード (`Short` および `Single`) の各引数の型が、3番目のオーバーロード (`Integer` および `Single`) の対応する型に拡大変換されるため、3番目のオーバーロードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="c9bd7-130">2番目のオーバーロードでは、より少ない拡大が必要になるため、コンパイラはこれを呼び出しに使用します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="c9bd7-131">2番目の呼び出しでは、コンパイラは、縮小に基づいてオーバーロードのいずれかを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="c9bd7-132">最初の呼び出しの場合と同じ理由で3番目のオーバーロードを削除します。これは、引数の型をより拡大して、2番目のオーバーロードを呼び出すことができるためです。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="c9bd7-133">ただし、コンパイラは1番目と2番目のオーバーロード間で解決できません。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="c9bd7-134">各には、もう一方の型に拡大変換する定義済みのパラメーター型が1つあります (`Short`に`Byte` ますが、`Double`には `Single` ます)。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="c9bd7-135">そのため、コンパイラはオーバーロードの解決エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="c9bd7-136">オーバーロードされた省略可能な引数と ParamArray 引数</span><span class="sxs-lookup"><span data-stu-id="c9bd7-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="c9bd7-137">1つのプロシージャの2つのオーバーロードが同じシグネチャを持つ場合、最後のパラメーターは[省略可能](../../../../visual-basic/language-reference/modifiers/optional.md)として宣言され、もう一方では[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)が宣言されますが、コンパイラは、そのプロシージャへの呼び出しを次のように解決します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="c9bd7-138">呼び出しで最後の引数がとして渡された場合</span><span class="sxs-lookup"><span data-stu-id="c9bd7-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="c9bd7-139">コンパイラは、最後の引数をとして宣言しているオーバーロードへの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="c9bd7-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="c9bd7-140">値なし (引数は省略されます)</span><span class="sxs-lookup"><span data-stu-id="c9bd7-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="c9bd7-141">単一の値</span><span class="sxs-lookup"><span data-stu-id="c9bd7-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="c9bd7-142">コンマ区切りリスト内の2つ以上の値</span><span class="sxs-lookup"><span data-stu-id="c9bd7-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="c9bd7-143">任意の長さの配列 (空の配列を含む)</span><span class="sxs-lookup"><span data-stu-id="c9bd7-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="c9bd7-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9bd7-144">See also</span></span>

- [<span data-ttu-id="c9bd7-145">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="c9bd7-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="c9bd7-146">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="c9bd7-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="c9bd7-147">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="c9bd7-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c9bd7-148">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c9bd7-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c9bd7-149">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="c9bd7-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c9bd7-150">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c9bd7-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c9bd7-151">方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="c9bd7-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c9bd7-152">方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="c9bd7-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c9bd7-153">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c9bd7-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="c9bd7-154">Overloads</span><span class="sxs-lookup"><span data-stu-id="c9bd7-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="c9bd7-155">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="c9bd7-155">Extension Methods</span></span>](./extension-methods.md)

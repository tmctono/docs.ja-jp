---
title: Overload Resolution
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
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266873"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="1e10e-102">オーバーロードの解決法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e10e-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="1e10e-103">Visual Basic コンパイラが、オーバーロードされた複数のバージョンで定義されているプロシージャの呼び出しを検出した場合、コンパイラは、呼び出すオーバーロードのどれを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e10e-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="1e10e-104">これは、次の手順を実行して行います。</span><span class="sxs-lookup"><span data-stu-id="1e10e-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="1e10e-105">**アクセシビリティ。**</span><span class="sxs-lookup"><span data-stu-id="1e10e-105">**Accessibility.**</span></span> <span data-ttu-id="1e10e-106">呼び出し元のコードが呼び出しを妨げるアクセス レベルを持つオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="1e10e-107">**パラメーターの数。**</span><span class="sxs-lookup"><span data-stu-id="1e10e-107">**Number of Parameters.**</span></span> <span data-ttu-id="1e10e-108">呼び出しで指定されたパラメーター数とは異なる数のパラメーターを定義するオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="1e10e-109">**パラメーター データ型。**</span><span class="sxs-lookup"><span data-stu-id="1e10e-109">**Parameter Data Types.**</span></span> <span data-ttu-id="1e10e-110">コンパイラは、拡張メソッドよりもインスタンス メソッドの優先を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="1e10e-111">プロシージャ呼び出しに一致するために拡大変換のみを必要とするインスタンス メソッドが見つかった場合、すべての拡張メソッドは削除され、コンパイラはインスタンス メソッドの候補のみを使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="1e10e-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="1e10e-112">そのようなインスタンス メソッドが見つからない場合は、インスタンス メソッドと拡張メソッドの両方を使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="1e10e-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="1e10e-113">この手順では、呼び出し元の引数のデータ型を、オーバーロードで定義されたパラメーター型に変換できないオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="1e10e-114">**縮小変換。**</span><span class="sxs-lookup"><span data-stu-id="1e10e-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="1e10e-115">呼び出し元の引数型から定義済みのパラメーター型への縮小変換を必要とするオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="1e10e-116">これは、型チェック スイッチ ([オプション Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)ステートメント`On` `Off`) が .</span><span class="sxs-lookup"><span data-stu-id="1e10e-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="1e10e-117">**最も広く表示されます。**</span><span class="sxs-lookup"><span data-stu-id="1e10e-117">**Least Widening.**</span></span> <span data-ttu-id="1e10e-118">コンパイラは、残りのオーバーロードをペアで考慮します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="1e10e-119">各ペアについて、定義されたパラメータのデータ型を比較します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="1e10e-120">オーバーロードの一方の型が、他のオーバーロードの対応する型にすべて拡大された場合、コンパイラは後者を削除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="1e10e-121">つまり、最小限の拡大を必要とするオーバーロードを保持します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="1e10e-122">**単一の候補。**</span><span class="sxs-lookup"><span data-stu-id="1e10e-122">**Single Candidate.**</span></span> <span data-ttu-id="1e10e-123">1 つのオーバーロードだけが残るまで、ペアでのオーバーロードの検討を続行し、そのオーバーロードへの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="1e10e-124">コンパイラがオーバーロードを 1 つの候補に減らすことができない場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1e10e-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="1e10e-125">次の図は、オーバーロードされたバージョンのセットのうちどれを呼び出すかを決定するプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="1e10e-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="1e10e-126">![オーバーロードの解決プロセスのフロー ダイアグラム](./media/overload-resolution/determine-overloaded-version.gif "オーバーロードされたバージョン間の解決")</span><span class="sxs-lookup"><span data-stu-id="1e10e-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>
  
 <span data-ttu-id="1e10e-127">このオーバーロード解決プロセスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="1e10e-128">最初の呼び出しでは、最初の引数 ( ) の型が対応`Short`するパラメーター ( )`Byte`の型に絞り込まれるため、コンパイラは最初のオーバーロードを削除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="1e10e-129">次に、2 番目のオーバーロード ( と ) の`Short`各`Single`引数型が 3 番目のオーバーロード (`Integer`と`Single`) の対応する型に広がるため、3 番目のオーバーロードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1e10e-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="1e10e-130">2 番目のオーバーロードは、必要な拡大が少ないので、コンパイラは呼び出しに使用します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="1e10e-131">2 番目の呼び出しでは、コンパイラは、狭くすることに基づいてオーバーロードを削除できません。</span><span class="sxs-lookup"><span data-stu-id="1e10e-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="1e10e-132">これは、引数型の拡大を減らして 2 番目のオーバーロードを呼び出すことができるため、最初の呼び出しと同じ理由で 3 番目のオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="1e10e-133">ただし、コンパイラは、最初と 2 番目のオーバーロードの間で解決できません。</span><span class="sxs-lookup"><span data-stu-id="1e10e-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="1e10e-134">各パラメーター`Byte`型には、もう一方の型 ( から ) に`Short`対応する`Single`型`Double`に拡大されるパラメータ型が定義されています。</span><span class="sxs-lookup"><span data-stu-id="1e10e-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="1e10e-135">そのため、コンパイラはオーバーロード解決エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="1e10e-136">オーバーロードされたオプション引数と ParamArray 引数</span><span class="sxs-lookup"><span data-stu-id="1e10e-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="1e10e-137">プロシージャの 2 つのオーバーロードに同じシグネチャがある場合、最後のパラメーターが一方で[Optional、](../../../../visual-basic/language-reference/modifiers/optional.md)もう一方のパラメータが[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)として宣言されている以外は、コンパイラは次のようにそのプロシージャの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="1e10e-138">呼び出しが最後の引数を次のように指定した場合</span><span class="sxs-lookup"><span data-stu-id="1e10e-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="1e10e-139">コンパイラは、最後の引数を次のように宣言するオーバーロードへの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="1e10e-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="1e10e-140">値なし (引数は省略)</span><span class="sxs-lookup"><span data-stu-id="1e10e-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="1e10e-141">単一の値</span><span class="sxs-lookup"><span data-stu-id="1e10e-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="1e10e-142">コンマ区切りリスト内の 2 つ以上の値</span><span class="sxs-lookup"><span data-stu-id="1e10e-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="1e10e-143">任意の長さの配列 (空の配列を含む)</span><span class="sxs-lookup"><span data-stu-id="1e10e-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="1e10e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e10e-144">See also</span></span>

- [<span data-ttu-id="1e10e-145">オプションのパラメータ</span><span class="sxs-lookup"><span data-stu-id="1e10e-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="1e10e-146">パラメータ配列</span><span class="sxs-lookup"><span data-stu-id="1e10e-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="1e10e-147">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="1e10e-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="1e10e-148">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1e10e-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="1e10e-149">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="1e10e-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="1e10e-150">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1e10e-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="1e10e-151">方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="1e10e-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="1e10e-152">方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="1e10e-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="1e10e-153">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="1e10e-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="1e10e-154">オーバー ロード</span><span class="sxs-lookup"><span data-stu-id="1e10e-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="1e10e-155">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="1e10e-155">Extension Methods</span></span>](./extension-methods.md)

---
title: オーバーロードの解決法 (Visual Basic)
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
ms.openlocfilehash: 4f81c7377423899c142c4270f325bbd7ed20b877
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312242"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="520af-102">オーバーロードの解決法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520af-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="520af-103">Visual Basic コンパイラには、いくつかのオーバー ロードされたバージョンで定義されているプロシージャへの呼び出しが検出されると、コンパイラは、オーバー ロードを呼び出すを決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="520af-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="520af-104">これは、次の手順を実行しています。</span><span class="sxs-lookup"><span data-stu-id="520af-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="520af-105">**アクセシビリティ。**</span><span class="sxs-lookup"><span data-stu-id="520af-105">**Accessibility.**</span></span> <span data-ttu-id="520af-106">呼び出し元のコードの呼び出しを防止するアクセス レベルを持つオーバー ロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="520af-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="520af-107">**パラメーターの数。**</span><span class="sxs-lookup"><span data-stu-id="520af-107">**Number of Parameters.**</span></span> <span data-ttu-id="520af-108">呼び出しでは指定された数と異なる数のパラメーターが定義されているオーバー ロードを除外します。</span><span class="sxs-lookup"><span data-stu-id="520af-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="520af-109">**パラメーターのデータ型。**</span><span class="sxs-lookup"><span data-stu-id="520af-109">**Parameter Data Types.**</span></span> <span data-ttu-id="520af-110">コンパイラは、拡張メソッドよりインスタンス メソッドの優先を使用します。</span><span class="sxs-lookup"><span data-stu-id="520af-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="520af-111">拡大に合わせてプロシージャの呼び出しの変換のみを必要とする任意のインスタンス メソッドが見つかった場合は、すべての拡張メソッドは削除され、インスタンス メソッドの候補をコンパイラが続行されます。</span><span class="sxs-lookup"><span data-stu-id="520af-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="520af-112">このようなインスタンス メソッドが見つからない場合は、インスタンスと拡張メソッドの両方を続行します。</span><span class="sxs-lookup"><span data-stu-id="520af-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="520af-113">この手順で、オーバー ロードで定義されているパラメーターの型に呼び出し元の引数のデータ型を変換できませんオーバー ロードを除外します。</span><span class="sxs-lookup"><span data-stu-id="520af-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="520af-114">**縮小変換をします。**</span><span class="sxs-lookup"><span data-stu-id="520af-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="520af-115">呼び出し元の引数の型から定義されたパラメーターの型への縮小変換を必要なオーバー ロードを除外します。</span><span class="sxs-lookup"><span data-stu-id="520af-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="520af-116">型チェックを切り替えるかどうかこれが true ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) は`On`または`Off`します。</span><span class="sxs-lookup"><span data-stu-id="520af-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="520af-117">**最小の拡大します。**</span><span class="sxs-lookup"><span data-stu-id="520af-117">**Least Widening.**</span></span> <span data-ttu-id="520af-118">コンパイラは、ペアで残りのオーバー ロードを検討します。</span><span class="sxs-lookup"><span data-stu-id="520af-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="520af-119">各ペアに定義されているパラメーターのデータ型を比較します。</span><span class="sxs-lookup"><span data-stu-id="520af-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="520af-120">内のすべてのオーバー ロードのいずれかの型は、他の対応する型に拡大変換する場合、コンパイラは後者を除外します。</span><span class="sxs-lookup"><span data-stu-id="520af-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="520af-121">これは、最小限の拡大が必要なオーバー ロードを保持します。</span><span class="sxs-lookup"><span data-stu-id="520af-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="520af-122">**1 つの候補。**</span><span class="sxs-lookup"><span data-stu-id="520af-122">**Single Candidate.**</span></span> <span data-ttu-id="520af-123">オーバー ロードを 1 つだけまでのペアがそのまま残り、オーバー ロードし、そのオーバー ロードの呼び出しを解決することを検討して続行します。</span><span class="sxs-lookup"><span data-stu-id="520af-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="520af-124">コンパイラは、オーバー ロードを 1 つの候補を減らすことができない、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="520af-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="520af-125">次の図は、一連の呼び出しのオーバー ロードされたバージョンを決定するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="520af-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="520af-126">![オーバー ロードの解決プロセスのフロー ダイアグラム](./media/overload-resolution/determine-overloaded-version.gif "オーバー ロードされたバージョンを解決します。")</span><span class="sxs-lookup"><span data-stu-id="520af-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>    
  
 <span data-ttu-id="520af-127">次の例では、このオーバー ロード解決プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="520af-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="520af-128">ため、最初の呼び出しで、コンパイラが最初のオーバー ロードを排除最初の引数の型 (`Short`) と対応するパラメーターの型へ縮小変換 (`Byte`)。</span><span class="sxs-lookup"><span data-stu-id="520af-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="520af-129">次に除去 3 番目のオーバー ロードは、2 番目のオーバー ロードに各引数を入力 (`Short`と`Single`) 3 番目のオーバー ロードでは、対応する型に拡大変換されます (`Integer`と`Single`)。</span><span class="sxs-lookup"><span data-stu-id="520af-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="520af-130">2 番目のオーバー ロードが必要な拡大が少ないので、コンパイラは、呼び出しの使用します。</span><span class="sxs-lookup"><span data-stu-id="520af-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="520af-131">2 番目の呼び出しでは、コンパイラは縮小に基づいてオーバー ロードのいずれかを取り除くことはできません。</span><span class="sxs-lookup"><span data-stu-id="520af-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="520af-132">以下の引数の型の拡大と 2 番目のオーバー ロードを呼び出すことができますので、同じ理由で最初の呼び出しのように、3 番目のオーバー ロードを除外します。</span><span class="sxs-lookup"><span data-stu-id="520af-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="520af-133">ただし、コンパイラは、最初と 2 番目のオーバー ロードの解決できません。</span><span class="sxs-lookup"><span data-stu-id="520af-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="520af-134">それぞれが、それ以外の対応する型を拡張する 1 つの定義されているパラメーターの型 (`Byte`に`Short`が`Single`に`Double`)。</span><span class="sxs-lookup"><span data-stu-id="520af-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="520af-135">そのため、コンパイラは、オーバー ロードの解決エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="520af-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="520af-136">省略可能なオーバー ロードと ParamArray 引数</span><span class="sxs-lookup"><span data-stu-id="520af-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="520af-137">最後のパラメーターを宣言する点を除いて、プロシージャの 2 つのオーバー ロードが同じシグネチャを持つ場合[(省略可能)](../../../../visual-basic/language-reference/modifiers/optional.md)で 1 つと[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)コンパイラとしてそのプロシージャの呼び出しを解決して、その他次に示します。</span><span class="sxs-lookup"><span data-stu-id="520af-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="520af-138">場合は、呼び出しとして最後の引数が指定されています</span><span class="sxs-lookup"><span data-stu-id="520af-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="520af-139">コンパイラは最後の引数として宣言するオーバー ロードの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="520af-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="520af-140">値 (引数を省略) ではありません。</span><span class="sxs-lookup"><span data-stu-id="520af-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="520af-141">1 つの値</span><span class="sxs-lookup"><span data-stu-id="520af-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="520af-142">コンマ区切りの一覧で、2 つ以上の値</span><span class="sxs-lookup"><span data-stu-id="520af-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="520af-143">(空の配列を含む) 任意の長さの配列</span><span class="sxs-lookup"><span data-stu-id="520af-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="520af-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="520af-144">See also</span></span>

- [<span data-ttu-id="520af-145">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="520af-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="520af-146">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="520af-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="520af-147">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="520af-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="520af-148">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="520af-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="520af-149">方法: 複数のバージョンのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="520af-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="520af-150">方法: オーバー ロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="520af-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="520af-151">方法: 省略可能なパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="520af-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="520af-152">方法: 不特定数のパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="520af-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="520af-153">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="520af-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="520af-154">Overloads</span><span class="sxs-lookup"><span data-stu-id="520af-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="520af-155">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="520af-155">Extension Methods</span></span>](./extension-methods.md)

---
title: '方法: 複数のバージョン (Visual Basic)、プロシージャの定義します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: fc7a8e18394b904f0c22a80f71dee091d4f786ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863832"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="eb42f-102">方法: 複数のバージョン (Visual Basic)、プロシージャの定義します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="eb42f-103">プロシージャを定義するには、複数のバージョンで*オーバー ロード*バージョンごとに同じ名前が別のパラメーター リストを使用しています。</span><span class="sxs-lookup"><span data-stu-id="eb42f-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="eb42f-104">オーバー ロードの目的では、名前で区別せずに密接に関連するいくつかのバージョンのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="eb42f-105">詳細については、「 [Procedure Overloading](./procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb42f-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="eb42f-106">プロシージャの複数のバージョンを定義するには</span><span class="sxs-lookup"><span data-stu-id="eb42f-106">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="eb42f-107">書き込みを`Sub`または`Function`を定義する手順の各バージョンの宣言ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="eb42f-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="eb42f-108">すべての宣言で同じプロシージャ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-108">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="eb42f-109">前に、`Sub`または`Function`各宣言キーワード、[オーバー ロード](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="eb42f-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="eb42f-110">必要に応じて省略できます`Overloads`宣言のいずれかに含める場合は、宣言する必要がありますに追加するすべての宣言。</span><span class="sxs-lookup"><span data-stu-id="eb42f-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="eb42f-111">次の各宣言ステートメントには、呼び出し元のコードがそのバージョンのパラメーター リストに一致する引数を提供する特定のケースを処理するプロシージャのコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="eb42f-112">必要はありませんをテストするパラメーターの呼び出し元のコードが提供されています。</span><span class="sxs-lookup"><span data-stu-id="eb42f-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="eb42f-113">Visual Basic では、プロシージャの対応するバージョンに制御を渡します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="eb42f-114">プロシージャの各バージョンの終了、`End Sub`または`End Function`に応じてステートメント。</span><span class="sxs-lookup"><span data-stu-id="eb42f-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb42f-115">例</span><span class="sxs-lookup"><span data-stu-id="eb42f-115">Example</span></span>  
 <span data-ttu-id="eb42f-116">次の例では、定義、`Sub`顧客の残高に対してトランザクションをポストするプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="eb42f-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="eb42f-117">使用して、`Overloads`キーワードを名前と、その他のアカウント番号での顧客を受け取ると、プロシージャの 2 つのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="eb42f-118">呼び出し元のコードは、いずれか、顧客 id を取得できます、`String`または`Integer`、いずれの場合も同じステートメントの呼び出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="eb42f-119">これらのバージョンを呼び出す方法については、`post`の手順を参照してください[方法。オーバー ロードされたプロシージャを呼び出す](./how-to-call-an-overloaded-procedure.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eb42f-120">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="eb42f-120">Compiling the Code</span></span>  
 <span data-ttu-id="eb42f-121">プロシージャ名が同じで別のパラメーター リストを持つ、オーバー ロードされたバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb42f-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb42f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb42f-122">See also</span></span>

- [<span data-ttu-id="eb42f-123">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="eb42f-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="eb42f-124">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="eb42f-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="eb42f-125">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eb42f-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="eb42f-126">方法: 省略可能なパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="eb42f-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="eb42f-127">方法: 不特定数のパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="eb42f-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="eb42f-128">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="eb42f-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="eb42f-129">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="eb42f-129">Overload Resolution</span></span>](./overload-resolution.md)

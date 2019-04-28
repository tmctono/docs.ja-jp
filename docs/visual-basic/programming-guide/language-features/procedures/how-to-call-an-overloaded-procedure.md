---
title: '方法: オーバー ロードされたプロシージャ (Visual Basic) を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d325c09516b4ce03facedce86f17ea49480b997a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666015"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="b13e5-102">方法: オーバー ロードされたプロシージャ (Visual Basic) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="b13e5-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="b13e5-103">プロシージャのオーバー ロードの利点は、呼び出しの柔軟性です。</span><span class="sxs-lookup"><span data-stu-id="b13e5-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="b13e5-104">呼び出し元のコードでは、プロシージャに渡すし、どの引数が渡される、1 つのプロシージャの名前を呼び出して必要な情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b13e5-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="b13e5-105">定義されている 1 つ以上のバージョンを含むプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="b13e5-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="b13e5-106">呼び出し元のコードで、プロシージャに渡すデータを決定します。</span><span class="sxs-lookup"><span data-stu-id="b13e5-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="b13e5-107">引数リスト内のデータの表示、通常の方法で、プロシージャの呼び出しを記述します。</span><span class="sxs-lookup"><span data-stu-id="b13e5-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="b13e5-108">引数がパラメーター リストで、プロシージャに対して定義されたバージョンのいずれかと一致してください。</span><span class="sxs-lookup"><span data-stu-id="b13e5-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="b13e5-109">呼び出すプロシージャのバージョンを決定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b13e5-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="b13e5-110">Visual Basic では、引数リストに一致するバージョンに制御を渡します。</span><span class="sxs-lookup"><span data-stu-id="b13e5-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="b13e5-111">次の例では、`post`プロシージャ内で宣言[方法。プロシージャの複数のバージョンを定義](./how-to-define-multiple-versions-of-a-procedure.md)します。</span><span class="sxs-lookup"><span data-stu-id="b13e5-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="b13e5-112">顧客 id を取得、かどうかを決定しますが、`String`または`Integer`、し、いずれの場合も同じ手順を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b13e5-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="b13e5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b13e5-113">See also</span></span>

- [<span data-ttu-id="b13e5-114">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b13e5-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b13e5-115">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="b13e5-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b13e5-116">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="b13e5-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="b13e5-117">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b13e5-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="b13e5-118">方法: 複数のバージョンのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="b13e5-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="b13e5-119">方法: 省略可能なパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="b13e5-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="b13e5-120">方法: 不特定数のパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="b13e5-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="b13e5-121">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="b13e5-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="b13e5-122">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="b13e5-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="b13e5-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="b13e5-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)

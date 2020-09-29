---
title: '方法: オーバーロードされたプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 68b8a9898cba846b63ed8ce9d8329516f12e90cb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075175"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="f4bed-102">方法: オーバーロードされたプロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4bed-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>

<span data-ttu-id="f4bed-103">プロシージャをオーバーロードする利点は、呼び出しの柔軟性にあります。</span><span class="sxs-lookup"><span data-stu-id="f4bed-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="f4bed-104">呼び出し元のコードは、プロシージャに渡す必要がある情報を取得し、渡す引数に関係なく、1 つのプロシージャ名を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f4bed-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="f4bed-105">複数のバージョンが定義されているプロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="f4bed-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="f4bed-106">呼び出し元のコードで、プロシージャに渡すデータを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4bed-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="f4bed-107">引数リストにデータを提示して、通常の方法でプロシージャ呼び出しを記述します。</span><span class="sxs-lookup"><span data-stu-id="f4bed-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="f4bed-108">引数が、プロシージャに対して定義されているいずれかのバージョンのパラメーター リストと一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f4bed-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="f4bed-109">呼び出すプロシージャのバージョンを決定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f4bed-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="f4bed-110">Visual Basic によって、引数リストと一致するバージョンに制御が渡されます。</span><span class="sxs-lookup"><span data-stu-id="f4bed-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="f4bed-111">次の例では、`post` プロシージャを呼び出します。これは「[方法:プロシージャの複数のバージョンを定義する](./how-to-define-multiple-versions-of-a-procedure.md)」で定義されています。</span><span class="sxs-lookup"><span data-stu-id="f4bed-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="f4bed-112">顧客 ID を取得し、それが `String` か `Integer` かを判断して、どちらの場合でも同じプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f4bed-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="f4bed-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4bed-113">See also</span></span>

- [<span data-ttu-id="f4bed-114">手順</span><span class="sxs-lookup"><span data-stu-id="f4bed-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f4bed-115">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="f4bed-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f4bed-116">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="f4bed-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="f4bed-117">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f4bed-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="f4bed-118">方法: プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="f4bed-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="f4bed-119">方法: 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="f4bed-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="f4bed-120">方法: 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="f4bed-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="f4bed-121">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="f4bed-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="f4bed-122">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="f4bed-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="f4bed-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="f4bed-123">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)

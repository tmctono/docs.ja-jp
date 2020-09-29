---
title: 序数が有効ではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871390"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="56bf7-102">序数が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="56bf7-102">Ordinal is not valid</span></span>

<span data-ttu-id="56bf7-103">ダイナミック リンク ライブラリ (DLL) への呼び出しが、`#num` 構文を使用して、プロシージャ名の代わりに数値を使用するように指定されています。</span><span class="sxs-lookup"><span data-stu-id="56bf7-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="56bf7-104">このエラーには、次のような原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="56bf7-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="56bf7-105">`#num` 式を序数に変換しようとして失敗しました。</span><span class="sxs-lookup"><span data-stu-id="56bf7-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="56bf7-106">指定された `#num` が、DLL 内の関数を指定していません。</span><span class="sxs-lookup"><span data-stu-id="56bf7-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="56bf7-107">タイプ ライブラリに無効な宣言が含まれているため、無効な序数が内部で使用されています。</span><span class="sxs-lookup"><span data-stu-id="56bf7-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="56bf7-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="56bf7-108">To correct this error</span></span>  
  
1. <span data-ttu-id="56bf7-109">式が有効な数値を表していること、または名前によってプロシージャを呼び出していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="56bf7-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="56bf7-110">`#num` が DLL 内の有効な関数を識別することを確認します。</span><span class="sxs-lookup"><span data-stu-id="56bf7-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="56bf7-111">コードをコメント アウトすることで、問題の原因となっているプロシージャ呼び出しを分離します。</span><span class="sxs-lookup"><span data-stu-id="56bf7-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="56bf7-112">プロシージャの `Declare` ステートメントを記述し、その問題をタイプ ライブラリのベンダーに報告します。</span><span class="sxs-lookup"><span data-stu-id="56bf7-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56bf7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="56bf7-113">See also</span></span>

- [<span data-ttu-id="56bf7-114">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="56bf7-114">Declare Statement</span></span>](../statements/declare-statement.md)

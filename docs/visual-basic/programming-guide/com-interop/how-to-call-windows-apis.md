---
title: '方法: Windows API を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 9de9f0fbcca291af0b6aadfd8e3fe7033708fbc6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347542"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="5f836-102">方法: Windows API を呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f836-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="5f836-103">この例は user32.dll 内の `MessageBox` 関数の定義と呼び出しを行い、そして文字列を渡しています。</span><span class="sxs-lookup"><span data-stu-id="5f836-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f836-104">使用例</span><span class="sxs-lookup"><span data-stu-id="5f836-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="5f836-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5f836-105">Compile the code</span></span>  
 <span data-ttu-id="5f836-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f836-106">This example requires:</span></span>  
  
- <span data-ttu-id="5f836-107"><xref:System> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="5f836-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5f836-108">堅牢性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="5f836-108">Robust Programming</span></span>  
 <span data-ttu-id="5f836-109">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5f836-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="5f836-110">メソッドが静的でない、または抽象メソッドである、または以前に定義されているメソッドの場合。</span><span class="sxs-lookup"><span data-stu-id="5f836-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="5f836-111">親の型がインターフェイスである、または*name*や*dllName*の長さが 0 の場合。</span><span class="sxs-lookup"><span data-stu-id="5f836-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="5f836-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="5f836-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="5f836-113">*name*または*dllName*が`Nothing`の場合。</span><span class="sxs-lookup"><span data-stu-id="5f836-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="5f836-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="5f836-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="5f836-115">含んでいる型が `CreateType` を使用して以前に作成されています。</span><span class="sxs-lookup"><span data-stu-id="5f836-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="5f836-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="5f836-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f836-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f836-117">See also</span></span>

- [<span data-ttu-id="5f836-118">プラットフォーム呼び出しの詳細</span><span class="sxs-lookup"><span data-stu-id="5f836-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="5f836-119">プラットフォーム呼び出しの例</span><span class="sxs-lookup"><span data-stu-id="5f836-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="5f836-120">アンマネージ DLL 関数の処理</span><span class="sxs-lookup"><span data-stu-id="5f836-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="5f836-121">[リフレクション出力によるメソッドの定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5f836-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="5f836-122">チュートリアル : Windows API の呼び出し</span><span class="sxs-lookup"><span data-stu-id="5f836-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="5f836-123">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="5f836-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)

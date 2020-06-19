---
title: '方法: Windows API を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 2c3bb599b79575180eb2b0ec89453f01901f94c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396844"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="1a54c-102">方法: Windows API を呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a54c-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="1a54c-103">この例では、`MessageBox` 関数を user32.dll に定義して呼び出し、文字列を関数に渡します。</span><span class="sxs-lookup"><span data-stu-id="1a54c-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a54c-104">例</span><span class="sxs-lookup"><span data-stu-id="1a54c-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="1a54c-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="1a54c-105">Compile the code</span></span>  
 <span data-ttu-id="1a54c-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a54c-106">This example requires:</span></span>  
  
- <span data-ttu-id="1a54c-107"><xref:System> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="1a54c-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1a54c-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="1a54c-108">Robust Programming</span></span>  
 <span data-ttu-id="1a54c-109">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a54c-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1a54c-110">メソッドが静的ではない、抽象である、または以前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="1a54c-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="1a54c-111">親の型がインターフェイスであるか、*name* または *dllName* の長さが 0 です。</span><span class="sxs-lookup"><span data-stu-id="1a54c-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="1a54c-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="1a54c-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="1a54c-113">*name* または *dllName* が `Nothing` です。</span><span class="sxs-lookup"><span data-stu-id="1a54c-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="1a54c-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="1a54c-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="1a54c-115">含んでいる型が `CreateType` を使用して以前に作成されています。</span><span class="sxs-lookup"><span data-stu-id="1a54c-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="1a54c-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="1a54c-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a54c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a54c-117">See also</span></span>

- [<span data-ttu-id="1a54c-118">プラットフォーム呼び出しの詳細</span><span class="sxs-lookup"><span data-stu-id="1a54c-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="1a54c-119">プラットフォーム呼び出しの例</span><span class="sxs-lookup"><span data-stu-id="1a54c-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="1a54c-120">アンマネージ DLL 関数の処理</span><span class="sxs-lookup"><span data-stu-id="1a54c-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="1a54c-121">[リフレクション出力によるメソッドの定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1a54c-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="1a54c-122">チュートリアル: Windows API の呼び出し</span><span class="sxs-lookup"><span data-stu-id="1a54c-122">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="1a54c-123">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="1a54c-123">COM Interop</span></span>](index.md)

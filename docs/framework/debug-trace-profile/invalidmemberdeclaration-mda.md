---
title: invalidMemberDeclaration MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 6033cd4178b2bc493794b5dcc527bc543ba24284
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216296"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="3cf62-102">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="3cf62-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="3cf62-103">`invalidMemberDeclaration` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、COM から呼び出されるメンバーのパラメーターをマーシャリングする方法を判断しているときに、エラーが発生したことを報告するためにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3cf62-104">現象</span><span class="sxs-lookup"><span data-stu-id="3cf62-104">Symptoms</span></span>  
 <span data-ttu-id="3cf62-105">マネージド メソッドが呼び出されることなく、COM にエラーの HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3cf62-106">原因</span><span class="sxs-lookup"><span data-stu-id="3cf62-106">Cause</span></span>  
 <span data-ttu-id="3cf62-107">ほとんどの場合、いずれかのパラメーターに互換性のない <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性があることが原因です。</span><span class="sxs-lookup"><span data-stu-id="3cf62-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3cf62-108">解決策</span><span class="sxs-lookup"><span data-stu-id="3cf62-108">Resolution</span></span>  
 <span data-ttu-id="3cf62-109">パラメーターで有効な <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3cf62-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="3cf62-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="3cf62-111">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="3cf62-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3cf62-112">出力</span><span class="sxs-lookup"><span data-stu-id="3cf62-112">Output</span></span>  
 <span data-ttu-id="3cf62-113">メンバー名、型名、およびエラー メッセージを含む情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="3cf62-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3cf62-114">構成</span><span class="sxs-lookup"><span data-stu-id="3cf62-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cf62-115">参照</span><span class="sxs-lookup"><span data-stu-id="3cf62-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3cf62-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="3cf62-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3cf62-117">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="3cf62-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)

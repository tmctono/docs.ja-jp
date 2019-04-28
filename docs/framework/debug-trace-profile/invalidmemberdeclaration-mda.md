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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e5b4cb4a04a79a748f4ea2292bac67a88a6e9f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754363"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="42fef-102">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="42fef-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="42fef-103">`invalidMemberDeclaration` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、COM から呼び出されるメンバーのパラメーターをマーシャリングする方法を判断しているときに、エラーが発生したことを報告するためにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="42fef-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="42fef-104">症状</span><span class="sxs-lookup"><span data-stu-id="42fef-104">Symptoms</span></span>  
 <span data-ttu-id="42fef-105">マネージド メソッドが呼び出されることなく、COM にエラーの HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="42fef-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="42fef-106">原因</span><span class="sxs-lookup"><span data-stu-id="42fef-106">Cause</span></span>  
 <span data-ttu-id="42fef-107">ほとんどの場合、いずれかのパラメーターに互換性のない <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性があることが原因です。</span><span class="sxs-lookup"><span data-stu-id="42fef-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="42fef-108">解像度</span><span class="sxs-lookup"><span data-stu-id="42fef-108">Resolution</span></span>  
 <span data-ttu-id="42fef-109">パラメーターで有効な <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="42fef-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="42fef-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="42fef-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="42fef-111">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="42fef-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="42fef-112">出力</span><span class="sxs-lookup"><span data-stu-id="42fef-112">Output</span></span>  
 <span data-ttu-id="42fef-113">メンバー名、型名、およびエラー メッセージを含む情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="42fef-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="42fef-114">構成</span><span class="sxs-lookup"><span data-stu-id="42fef-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42fef-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="42fef-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="42fef-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="42fef-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="42fef-117">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="42fef-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

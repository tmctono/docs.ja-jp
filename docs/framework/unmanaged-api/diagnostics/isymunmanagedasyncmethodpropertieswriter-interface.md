---
title: ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82fcddd7a3f89a92cc79285930b30342333fbec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940102"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="a8d87-102">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8d87-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="a8d87-103">各メソッドのシンボルのオプションの非同期メソッドの情報を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a8d87-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="a8d87-104">開かれているメソッド; で常に使用します。つまり、呼び出しの間で、 [OpenMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)と[CloseMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8d87-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8d87-105">構文</span><span class="sxs-lookup"><span data-stu-id="a8d87-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="a8d87-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8d87-106">Methods</span></span>  
 <span data-ttu-id="a8d87-107">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8d87-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="a8d87-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8d87-108">Method</span></span>|<span data-ttu-id="a8d87-109">説明</span><span class="sxs-lookup"><span data-stu-id="a8d87-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8d87-110">DefineAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="a8d87-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="a8d87-111">非同期のグループを定義、現在のメソッドでの操作を待機します。</span><span class="sxs-lookup"><span data-stu-id="a8d87-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="a8d87-112">各 yield オフセットでは、潜在的な yield を識別する、await の戻り命令と一致します。</span><span class="sxs-lookup"><span data-stu-id="a8d87-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="a8d87-113">各`breakpointMethod` / `breakpointOffset`ペアを識別、非同期操作が再開されます。 別のメソッドである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8d87-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="a8d87-114">DefineCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a8d87-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="a8d87-115">IL オフセットの非同期メソッドをラップする catch のコンパイラによって生成されたハンドラーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a8d87-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="a8d87-116">生成された catch の IL オフセットは、ユーザー コード メソッドが発生する場合でも、非ユーザー コードの場合と同様に、catch を処理するために、デバッガーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8d87-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="a8d87-117">具体的への応答で使用される、 **CatchHandlerFound**例外イベント。</span><span class="sxs-lookup"><span data-stu-id="a8d87-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="a8d87-118">DefineKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="a8d87-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="a8d87-119">非同期操作を開始する開始メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="a8d87-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8d87-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8d87-120">Requirements</span></span>  
 <span data-ttu-id="a8d87-121">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a8d87-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d87-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8d87-122">See also</span></span>

- [<span data-ttu-id="a8d87-123">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8d87-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

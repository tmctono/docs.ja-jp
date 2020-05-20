---
title: ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 360d1150b0accd6a070fa36531e570d222787cee
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441761"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="91004-102">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91004-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="91004-103">各メソッドシンボルに対してオプションの非同期メソッド情報を定義できます。</span><span class="sxs-lookup"><span data-stu-id="91004-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="91004-104">開いているメソッドでは常にを使用します。つまり、 [Openmethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)と[closemethod メソッド](isymunmanagedwriter-closemethod-method.md)の呼び出しの間です。</span><span class="sxs-lookup"><span data-stu-id="91004-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91004-105">構文</span><span class="sxs-lookup"><span data-stu-id="91004-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="91004-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="91004-106">Methods</span></span>  
 <span data-ttu-id="91004-107">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91004-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="91004-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="91004-108">Method</span></span>|<span data-ttu-id="91004-109">説明</span><span class="sxs-lookup"><span data-stu-id="91004-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91004-110">DefineAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="91004-110">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="91004-111">現在のメソッドで非同期 await 操作のグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="91004-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="91004-112">各 yield オフセットは await の戻り命令に一致し、潜在的な yield を識別します。</span><span class="sxs-lookup"><span data-stu-id="91004-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="91004-113">各 `breakpointMethod` / `breakpointOffset` ペアは、非同期操作が再開される場所を識別します。これは、別のメソッドに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91004-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="91004-114">DefineCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="91004-114">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="91004-115">非同期メソッドをラップする、コンパイラによって生成される catch ハンドラーの IL オフセットを設定します。</span><span class="sxs-lookup"><span data-stu-id="91004-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="91004-116">生成された catch の IL オフセットは、ユーザーコードメソッドで発生する可能性があっても、catch を非ユーザーコードとして処理するためにデバッガーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="91004-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="91004-117">特に、 **CatchHandlerFound** exception イベントに応答して使用されます。</span><span class="sxs-lookup"><span data-stu-id="91004-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="91004-118">DefineKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="91004-118">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="91004-119">非同期操作を開始する開始メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="91004-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91004-120">要件</span><span class="sxs-lookup"><span data-stu-id="91004-120">Requirements</span></span>  
 <span data-ttu-id="91004-121">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="91004-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91004-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="91004-122">See also</span></span>

- [<span data-ttu-id="91004-123">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91004-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

---
title: ISymUnmanagedAsyncMethod インターフェイス
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 0b8adba9dbffbdc47bb526cef9aad3ffa4b48065
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129222"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="b923f-102">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b923f-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="b923f-103">このインターフェイスは、 [ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)への読み取り補数です。</span><span class="sxs-lookup"><span data-stu-id="b923f-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b923f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b923f-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="b923f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-105">Methods</span></span>  
 <span data-ttu-id="b923f-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b923f-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b923f-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-107">Method</span></span>|<span data-ttu-id="b923f-108">説明</span><span class="sxs-lookup"><span data-stu-id="b923f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b923f-109">GetAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="b923f-110">「 [DefineAsyncStepInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b923f-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="b923f-111">GetAsyncStepInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="b923f-112">「 [DefineAsyncStepInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b923f-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="b923f-113">GetCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="b923f-114">「 [DefineCatchHandlerILOffset メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b923f-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="b923f-115">GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="b923f-116">「 [DefineKickoffMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b923f-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="b923f-117">HasCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="b923f-118">「 [DefineCatchHandlerILOffset メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b923f-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="b923f-119">IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="b923f-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="b923f-120">メソッドに非同期情報があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b923f-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="b923f-121">このメソッドが `FALSE` 返す場合は、このインターフェイスで他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b923f-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="b923f-122">これらはすべて、この場合 `E_UNEXPECTED` を返します。</span><span class="sxs-lookup"><span data-stu-id="b923f-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b923f-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="b923f-123">Requirements</span></span>  
 <span data-ttu-id="b923f-124">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="b923f-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b923f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b923f-125">See also</span></span>

- [<span data-ttu-id="b923f-126">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b923f-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

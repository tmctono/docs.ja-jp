---
title: ISymUnmanagedAsyncMethod インターフェイス
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: fef1af75587b889afad9cb5b93d0cd722294006b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441813"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="56d4e-102">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56d4e-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="56d4e-103">このインターフェイスは、 [ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス](isymunmanagedasyncmethodpropertieswriter-interface.md)への読み取り補数です。</span><span class="sxs-lookup"><span data-stu-id="56d4e-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="56d4e-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="56d4e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-105">Methods</span></span>  
 <span data-ttu-id="56d4e-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="56d4e-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="56d4e-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-107">Method</span></span>|<span data-ttu-id="56d4e-108">説明</span><span class="sxs-lookup"><span data-stu-id="56d4e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56d4e-109">GetAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="56d4e-110">「 [DefineAsyncStepInfo メソッド](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d4e-110">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="56d4e-111">GetAsyncStepInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="56d4e-112">「 [DefineAsyncStepInfo メソッド](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d4e-112">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="56d4e-113">GetCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="56d4e-114">「 [DefineCatchHandlerILOffset メソッド](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d4e-114">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="56d4e-115">GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="56d4e-116">「 [DefineKickoffMethod メソッド](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d4e-116">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="56d4e-117">HasCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="56d4e-118">「 [DefineCatchHandlerILOffset メソッド](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d4e-118">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="56d4e-119">IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-119">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="56d4e-120">メソッドに非同期情報があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="56d4e-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="56d4e-121">このメソッドがを返す場合 `FALSE` 、このインターフェイス内の他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="56d4e-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="56d4e-122">これらはすべて、 `E_UNEXPECTED` この場合はを返します。</span><span class="sxs-lookup"><span data-stu-id="56d4e-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56d4e-123">要件</span><span class="sxs-lookup"><span data-stu-id="56d4e-123">Requirements</span></span>  
 <span data-ttu-id="56d4e-124">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="56d4e-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d4e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="56d4e-125">See also</span></span>

- [<span data-ttu-id="56d4e-126">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56d4e-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

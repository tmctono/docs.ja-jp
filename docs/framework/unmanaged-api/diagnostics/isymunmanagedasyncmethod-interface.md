---
title: ISymUnmanagedAsyncMethod インターフェイス
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd524446cd9fd5cf9c067ab5778a654ed000ffb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179804"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="40b66-102">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40b66-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="40b66-103">このインターフェイスは、読み取りの補足[ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="40b66-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b66-104">構文</span><span class="sxs-lookup"><span data-stu-id="40b66-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="40b66-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-105">Methods</span></span>  
 <span data-ttu-id="40b66-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="40b66-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="40b66-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-107">Method</span></span>|<span data-ttu-id="40b66-108">説明</span><span class="sxs-lookup"><span data-stu-id="40b66-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40b66-109">GetAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="40b66-110">参照してください[DefineAsyncStepInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="40b66-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="40b66-111">GetAsyncStepInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="40b66-112">参照してください[DefineAsyncStepInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="40b66-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="40b66-113">GetCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="40b66-114">参照してください[DefineCatchHandlerILOffset メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="40b66-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="40b66-115">GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="40b66-116">参照してください[DefineKickoffMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="40b66-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="40b66-117">HasCatchHandlerILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="40b66-118">参照してください[DefineCatchHandlerILOffset メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="40b66-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="40b66-119">IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="40b66-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="40b66-120">かどうかのかどうか、メソッドは非同期の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="40b66-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="40b66-121">このメソッドが戻る場合`FALSE`し、このインターフェイスで、他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="40b66-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="40b66-122">すべての戻り値は`E_UNEXPECTED`ここでします。</span><span class="sxs-lookup"><span data-stu-id="40b66-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40b66-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="40b66-123">Requirements</span></span>  
 <span data-ttu-id="40b66-124">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="40b66-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b66-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="40b66-125">See also</span></span>

- [<span data-ttu-id="40b66-126">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40b66-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

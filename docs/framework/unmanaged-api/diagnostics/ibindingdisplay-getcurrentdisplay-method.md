---
title: IBindingDisplay::GetCurrentDisplay メソッド
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 9294dbf1caddd4b607185de54efd2b4764e6ca35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448498"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="b4679-102">IBindingDisplay::GetCurrentDisplay メソッド</span><span class="sxs-lookup"><span data-stu-id="b4679-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="b4679-103">Returns the current binding display information.</span><span class="sxs-lookup"><span data-stu-id="b4679-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4679-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4679-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4679-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4679-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="b4679-106">[out, retval] A pointer to a safearray containing the binding display information.</span><span class="sxs-lookup"><span data-stu-id="b4679-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4679-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4679-107">Remarks</span></span>  
 <span data-ttu-id="b4679-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span><span class="sxs-lookup"><span data-stu-id="b4679-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="b4679-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="b4679-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4679-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="b4679-110">Requirements</span></span>  
 <span data-ttu-id="b4679-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4679-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4679-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="b4679-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="b4679-113">**Library:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="b4679-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="b4679-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4679-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4679-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4679-115">See also</span></span>

- [<span data-ttu-id="b4679-116">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4679-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="b4679-117">InitializeForProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="b4679-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)

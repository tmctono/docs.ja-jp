---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7c72d0766580f9aa3aa678aacd872b804172a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131431"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="d2eca-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d2eca-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="d2eca-103">参照してください[DefineAsyncStepInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2eca-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2eca-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2eca-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2eca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2eca-105">Parameters</span></span>  
  
|<span data-ttu-id="d2eca-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2eca-106">Parameter</span></span>|<span data-ttu-id="d2eca-107">説明</span><span class="sxs-lookup"><span data-stu-id="d2eca-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d2eca-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d2eca-108">Return Value</span></span>  
 <span data-ttu-id="d2eca-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="d2eca-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2eca-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d2eca-110">Requirements</span></span>  
 <span data-ttu-id="d2eca-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d2eca-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2eca-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2eca-112">See also</span></span>

- [<span data-ttu-id="d2eca-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2eca-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

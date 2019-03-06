---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34792ddc7d32c89f6572a48e4636a63881611b88
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473553"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="71212-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="71212-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="71212-103">参照してください[DefineAsyncStepInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="71212-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71212-104">構文</span><span class="sxs-lookup"><span data-stu-id="71212-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71212-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71212-105">Parameters</span></span>  
  
|<span data-ttu-id="71212-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71212-106">Parameter</span></span>|<span data-ttu-id="71212-107">説明</span><span class="sxs-lookup"><span data-stu-id="71212-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="71212-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="71212-108">Return Value</span></span>  
 <span data-ttu-id="71212-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="71212-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71212-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="71212-110">Requirements</span></span>  
 <span data-ttu-id="71212-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="71212-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71212-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="71212-112">See also</span></span>
- [<span data-ttu-id="71212-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71212-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

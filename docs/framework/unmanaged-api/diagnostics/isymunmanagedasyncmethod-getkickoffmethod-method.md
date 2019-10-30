---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 58daec30b4cbae9cfaab27d4ce76521ba839cf83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139848"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="fa9d5-102">ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="fa9d5-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="fa9d5-103">「 [DefineKickoffMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9d5-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa9d5-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa9d5-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa9d5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa9d5-105">Parameters</span></span>  
  
|<span data-ttu-id="fa9d5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa9d5-106">Parameter</span></span>|<span data-ttu-id="fa9d5-107">説明</span><span class="sxs-lookup"><span data-stu-id="fa9d5-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="fa9d5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="fa9d5-108">Return Value</span></span>  
 <span data-ttu-id="fa9d5-109">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="fa9d5-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa9d5-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="fa9d5-110">Requirements</span></span>  
 <span data-ttu-id="fa9d5-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="fa9d5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9d5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa9d5-112">See also</span></span>

- [<span data-ttu-id="fa9d5-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa9d5-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

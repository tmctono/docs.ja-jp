---
title: ICorDebugMDA::GetDescription メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: bfe77982b88b2fc96dc2846b9db04df28bfc0c38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131448"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="33b51-102">ICorDebugMDA::GetDescription メソッド</span><span class="sxs-lookup"><span data-stu-id="33b51-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="33b51-103">によって表されるマネージデバッグアシスタント (MDA) の説明を含む文字列を[取得します](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="33b51-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b51-104">構文</span><span class="sxs-lookup"><span data-stu-id="33b51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33b51-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="33b51-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="33b51-106">から説明を格納する文字列バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="33b51-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="33b51-107">入出力文字列バッファーで返されたバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="33b51-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="33b51-108">入出力MDA の説明を格納している文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="33b51-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33b51-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="33b51-109">Remarks</span></span>  
 <span data-ttu-id="33b51-110">文字列の長さは0にすることができます。</span><span class="sxs-lookup"><span data-stu-id="33b51-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b51-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="33b51-111">Requirements</span></span>  
 <span data-ttu-id="33b51-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33b51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b51-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33b51-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33b51-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33b51-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33b51-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33b51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b51-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="33b51-116">See also</span></span>

- [<span data-ttu-id="33b51-117">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33b51-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="33b51-118">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="33b51-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93721815d44d7c348860742ab2c8b237cb8f5f67
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469588"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="ee261-102">ICorDebugMDA::GetDescription メソッド</span><span class="sxs-lookup"><span data-stu-id="ee261-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="ee261-103">によって表されるマネージ デバッグ アシスタント (MDA) の説明を表す文字列を取得します[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee261-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee261-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee261-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee261-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee261-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ee261-106">[in]説明を格納する文字列バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="ee261-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ee261-107">[out]文字列バッファーに返されるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ee261-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="ee261-108">[out]MDA の説明を表す文字列のバッファー。</span><span class="sxs-lookup"><span data-stu-id="ee261-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee261-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee261-109">Remarks</span></span>  
 <span data-ttu-id="ee261-110">文字列が長さ 0 を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ee261-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee261-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee261-111">Requirements</span></span>  
 <span data-ttu-id="ee261-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee261-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee261-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee261-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee261-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee261-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee261-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee261-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee261-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee261-116">See also</span></span>
- [<span data-ttu-id="ee261-117">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee261-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="ee261-118">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="ee261-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

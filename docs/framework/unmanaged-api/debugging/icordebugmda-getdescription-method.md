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
ms.openlocfilehash: 998d4baf03123f1ffc174b2a7aeed0ff4a25b001
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723681"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="c8e4d-102">ICorDebugMDA::GetDescription メソッド</span><span class="sxs-lookup"><span data-stu-id="c8e4d-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="c8e4d-103">によって表されるマネージ デバッグ アシスタント (MDA) の説明を表す文字列を取得します[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8e4d-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8e4d-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8e4d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8e4d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c8e4d-106">[in]説明を格納する文字列バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c8e4d-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c8e4d-107">[out]文字列バッファーに返されるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c8e4d-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c8e4d-108">[out]MDA の説明を表す文字列のバッファー。</span><span class="sxs-lookup"><span data-stu-id="c8e4d-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8e4d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8e4d-109">Remarks</span></span>  
 <span data-ttu-id="c8e4d-110">文字列が長さ 0 を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8e4d-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8e4d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8e4d-111">Requirements</span></span>  
 <span data-ttu-id="c8e4d-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e4d-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8e4d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8e4d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8e4d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8e4d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e4d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8e4d-116">See also</span></span>

- [<span data-ttu-id="c8e4d-117">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8e4d-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="c8e4d-118">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="c8e4d-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

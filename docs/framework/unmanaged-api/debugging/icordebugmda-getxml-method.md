---
title: ICorDebugMDA::GetXML メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003a6546b3316f2a2a65bce4537c60dcf62b3197
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752852"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="73290-102">ICorDebugMDA::GetXML メソッド</span><span class="sxs-lookup"><span data-stu-id="73290-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="73290-103">によって表されるマネージ デバッグ アシスタント (MDA) に関連付けられている完全な XML ストリームを取得して[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="73290-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73290-104">構文</span><span class="sxs-lookup"><span data-stu-id="73290-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73290-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73290-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="73290-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="73290-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="73290-107">[out]XML ストリームの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="73290-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="73290-108">[out]XML ストリームを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="73290-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="73290-109">配列は空にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="73290-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73290-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="73290-110">Remarks</span></span>  
 <span data-ttu-id="73290-111">`GetXML`メソッドできます関連付けられている XML ストリームのサイズによっては、パフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73290-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73290-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="73290-112">Requirements</span></span>  
 <span data-ttu-id="73290-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73290-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73290-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73290-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73290-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73290-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73290-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73290-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73290-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="73290-117">See also</span></span>

- [<span data-ttu-id="73290-118">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73290-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="73290-119">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="73290-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

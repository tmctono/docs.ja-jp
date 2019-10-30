---
title: ICorDebugModule::GetName メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: b27e7a2cdcbfc3a88a734230118d99c2dd5c700e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129538"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="b2599-102">ICorDebugModule::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="b2599-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="b2599-103">モジュールのファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2599-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2599-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2599-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2599-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2599-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="b2599-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="b2599-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b2599-107">から返された名前の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2599-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="b2599-108">入出力返された名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="b2599-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2599-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2599-109">Remarks</span></span>  
 <span data-ttu-id="b2599-110">モジュールのファイル名がディスク上の名前と一致する場合、`GetName` メソッドは S_OK HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="b2599-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="b2599-111">動的またはメモリ内モジュールのような名前の場合、`GetName` は S_FALSE HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="b2599-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2599-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="b2599-112">Requirements</span></span>  
 <span data-ttu-id="b2599-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2599-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2599-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2599-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2599-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2599-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2599-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2599-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2599-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2599-117">See also</span></span>

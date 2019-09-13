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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7f62385031967c164915fd31735a6d962f557fa
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894988"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="ce2cc-102">ICorDebugModule::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="ce2cc-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="ce2cc-103">モジュールのファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce2cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce2cc-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce2cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce2cc-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="ce2cc-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ce2cc-107">から返された名前の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce2cc-108">入出力返された名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce2cc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce2cc-109">Remarks</span></span>  
 <span data-ttu-id="ce2cc-110">モジュール`GetName`のファイル名がディスク上の名前と一致する場合、メソッドは S_OK HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="ce2cc-111">`GetName`動的またはメモリ内モジュールなどで、名前が使用されている場合は S_FALSE HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce2cc-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ce2cc-112">Requirements</span></span>  
 <span data-ttu-id="ce2cc-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce2cc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce2cc-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ce2cc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce2cc-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="ce2cc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce2cc-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce2cc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2cc-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce2cc-117">See also</span></span>

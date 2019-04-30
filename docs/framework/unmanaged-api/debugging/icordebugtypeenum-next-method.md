---
title: ICorDebugTypeEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d47f14ff2adb37fca16cf6774a2b80cb2e074b17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993773"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="9f655-102">ICorDebugTypeEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="9f655-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="9f655-103">指定された"ICorDebugType"インスタンスの数を取得`celt`列挙体の現在位置から。</span><span class="sxs-lookup"><span data-stu-id="9f655-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f655-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f655-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f655-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f655-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9f655-106">[in]数`ICorDebugType`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f655-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="9f655-107">[out]それぞれが指すポインターの配列、`ICorDebugType`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f655-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9f655-108">[out]数へのポインター`ICorDebugType`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="9f655-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="9f655-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="9f655-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f655-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f655-110">Requirements</span></span>  
 <span data-ttu-id="9f655-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f655-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f655-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f655-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f655-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f655-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f655-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f655-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f655-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f655-115">See also</span></span>

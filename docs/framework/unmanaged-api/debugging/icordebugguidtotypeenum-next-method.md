---
title: ICorDebugGuidToTypeEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160ddbf9be8eb9f3b99d159aa8b36a22b58a9f55
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025807"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="074e4-102">ICorDebugGuidToTypeEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="074e4-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="074e4-103">指定した数を取得[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)インスタンス情報を入力する Guid にマップします。</span><span class="sxs-lookup"><span data-stu-id="074e4-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="074e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="074e4-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="074e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="074e4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="074e4-106">[in]取得する GUID 型への対応付けオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="074e4-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="074e4-107">[out]それぞれが指すポインターの配列を[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Windows ランタイムの GUID を対応する ICorDebugType オブジェクトにマップするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="074e4-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="074e4-108">[out]数へのポインター [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)で実際に返されるオブジェクト`values`します。</span><span class="sxs-lookup"><span data-stu-id="074e4-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="074e4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="074e4-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="074e4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="074e4-110">Requirements</span></span>  
 <span data-ttu-id="074e4-111">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="074e4-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="074e4-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="074e4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="074e4-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="074e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="074e4-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="074e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="074e4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="074e4-115">See also</span></span>

- [<span data-ttu-id="074e4-116">ICorDebugGuidToTypeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="074e4-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="074e4-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="074e4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

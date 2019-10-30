---
title: 'ICorDebugCode4:: EnumerateVariableHomes メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 850cbd2367dddd9f46375817e271cb8e7183cf64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121097"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="c0607-102">ICorDebugCode4:: EnumerateVariableHomes メソッド</span><span class="sxs-lookup"><span data-stu-id="c0607-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="c0607-103">関数のローカル変数および引数に対する列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0607-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0607-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0607-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0607-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0607-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c0607-106">関数内のローカル変数および引数の列挙子である、の[型](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)のオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0607-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0607-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0607-107">Remarks</span></span>  
 <span data-ttu-id="c0607-108">"ICorDebugEnum" インターフェイスから派生した標準列挙子で[ある、表示変数](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)[ホーム](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクトを列挙できます。</span><span class="sxs-lookup"><span data-stu-id="c0607-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="c0607-109">コレクションには、同じスロットまたは引数インデックスに対して、関数内の異なるポイントに異なる[ホーム](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクトが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0607-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0607-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="c0607-110">Requirements</span></span>  
 <span data-ttu-id="c0607-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0607-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0607-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0607-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0607-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0607-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0607-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0607-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0607-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0607-115">See also</span></span>

- [<span data-ttu-id="c0607-116">ICorDebugCode4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0607-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="c0607-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0607-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

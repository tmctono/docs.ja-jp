---
title: は、次のメソッドを実行します。
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 9c2c16789fb61099c9b7c58154810739d225af1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121922"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="af4da-102">は、次のメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af4da-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="af4da-103">関数内のローカル変数および引数に関する情報を格納している指定された数の表示変数[home](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="af4da-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af4da-104">構文</span><span class="sxs-lookup"><span data-stu-id="af4da-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af4da-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af4da-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="af4da-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="af4da-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="af4da-107">ポインターの配列。各ポインターは、関数のローカル変数または引数に関する情報を提供[する、の各オブジェクトを](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)参照します。</span><span class="sxs-lookup"><span data-stu-id="af4da-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="af4da-108">入出力実際にオブジェクトで返されたインスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="af4da-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af4da-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="af4da-109">Return Value</span></span>  
 <span data-ttu-id="af4da-110">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="af4da-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="af4da-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af4da-111">HRESULT</span></span>|<span data-ttu-id="af4da-112">説明</span><span class="sxs-lookup"><span data-stu-id="af4da-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="af4da-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="af4da-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="af4da-114">`pceltFetched`に反映された実際に取得されたインスタンスの数が、要求されたインスタンスの数より少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="af4da-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af4da-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="af4da-115">Remarks</span></span>  
 <span data-ttu-id="af4da-116">[次](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)のメソッドは、列挙子の現在位置から最大 `celt` オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="af4da-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="af4da-117">メソッドから制御が戻ったときに、`pceltFetched` 取得したオブジェクトの実際の数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="af4da-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af4da-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="af4da-118">Requirements</span></span>  
 <span data-ttu-id="af4da-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af4da-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af4da-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af4da-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af4da-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af4da-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af4da-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af4da-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4da-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="af4da-123">See also</span></span>

- [<span data-ttu-id="af4da-124">ICorDebugVariableHomeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af4da-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="af4da-125">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af4da-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

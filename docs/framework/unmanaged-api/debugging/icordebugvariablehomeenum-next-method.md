---
title: ICorDebugVariableHomeEnum::Next メソッド
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be1ba87ae979911dd21647569725eafa2c80ffa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768811"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="cdfec-102">ICorDebugVariableHomeEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="cdfec-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="cdfec-103">指定した数を取得[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)については、ローカル変数と関数の引数を格納するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cdfec-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdfec-104">構文</span><span class="sxs-lookup"><span data-stu-id="cdfec-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdfec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cdfec-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cdfec-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="cdfec-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="cdfec-107">それぞれが指すポインターの配列を[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)ローカル変数または関数の引数に関する情報を提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cdfec-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cdfec-108">[out]インスタンスの数は、実際には、オブジェクトで返されます。</span><span class="sxs-lookup"><span data-stu-id="cdfec-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdfec-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="cdfec-109">Return Value</span></span>  
 <span data-ttu-id="cdfec-110">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="cdfec-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="cdfec-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cdfec-111">HRESULT</span></span>|<span data-ttu-id="cdfec-112">説明</span><span class="sxs-lookup"><span data-stu-id="cdfec-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cdfec-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="cdfec-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cdfec-114">インスタンスの実際の数の取得に反映される`pceltFetched`が要求されたインスタンスの数未満です。</span><span class="sxs-lookup"><span data-stu-id="cdfec-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdfec-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdfec-115">Remarks</span></span>  
 <span data-ttu-id="cdfec-116">[ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)メソッドの最大値を取得する`celt`オブジェクトの列挙子の現在位置から始まります。</span><span class="sxs-lookup"><span data-stu-id="cdfec-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="cdfec-117">メソッドが戻るときに`pceltFetched`取得したオブジェクトの実際の数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdfec-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdfec-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="cdfec-118">Requirements</span></span>  
 <span data-ttu-id="cdfec-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfec-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdfec-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdfec-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdfec-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdfec-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdfec-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdfec-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfec-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdfec-123">See also</span></span>

- [<span data-ttu-id="cdfec-124">ICorDebugVariableHomeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdfec-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="cdfec-125">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdfec-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

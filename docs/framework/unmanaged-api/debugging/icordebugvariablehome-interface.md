---
title: ICorDebugVariableHome インターフェイス
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: 306a07450b8ae6d29875ca0cc4679390472e4d1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121039"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="cd9f7-102">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd9f7-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="cd9f7-103">関数のローカル変数または引数を表します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd9f7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-104">Methods</span></span>  
  
|<span data-ttu-id="cd9f7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-105">Method</span></span>|<span data-ttu-id="cd9f7-106">説明</span><span class="sxs-lookup"><span data-stu-id="cd9f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd9f7-107">GetArgumentIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="cd9f7-108">関数の引数のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="cd9f7-109">GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="cd9f7-110">この `ICorDebugVariableHome` オブジェクトを含む "コード" インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="cd9f7-111">GetLiveRange メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="cd9f7-112">この変数がライブであるネイティブ範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="cd9f7-113">GetLocationType メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="cd9f7-114">変数のネイティブな場所の型を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="cd9f7-115">GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="cd9f7-116">変数の基本レジスタからのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="cd9f7-117">GetRegister メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="cd9f7-118">`VLT_REGISTER`の場所の種類を持つ変数と、場所の種類が `VLT_REGISTER_RELATIVE`の変数の基本レジスタを含むレジスタを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="cd9f7-119">GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9f7-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="cd9f7-120">ローカル変数のマネージドスロットインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cd9f7-121">例</span><span class="sxs-lookup"><span data-stu-id="cd9f7-121">Example</span></span>  
 <span data-ttu-id="cd9f7-122">次のコード片では、`pCode4`という名前の[ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="cd9f7-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="cd9f7-123">Requirements</span></span>  
 <span data-ttu-id="cd9f7-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd9f7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9f7-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd9f7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd9f7-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd9f7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd9f7-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9f7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9f7-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd9f7-128">See also</span></span>

- [<span data-ttu-id="cd9f7-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd9f7-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cd9f7-130">ICorDebugVariableHomeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd9f7-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)

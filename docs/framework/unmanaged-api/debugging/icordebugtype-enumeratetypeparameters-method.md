---
title: ICorDebugType::EnumerateTypeParameters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: 57a82e4ec106fead105cc7f200e7e56026004328
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122377"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="cc445-102">ICorDebugType::EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="cc445-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="cc445-103">このテキストの型によって参照されるクラスの <xref:System.Type> パラメーターを格納している、テキスト型へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="cc445-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc445-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc445-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc445-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc445-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="cc445-106">入出力型のパラメーターを格納している `ICorDebugTypeEnum` のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cc445-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc445-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cc445-107">Remarks</span></span>  
 <span data-ttu-id="cc445-108">ELEMENT_TYPE_CLASS、ELEMENT_TYPE_VALUETYPE、ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF、ELEMENT_TYPE_PTR、または ELEMENT_TYPE_FNPTR の CorElementType 値が返された[場合は、](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) `EnumerateTypeParameters` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc445-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="cc445-109">パラメーターの数と順序は、型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cc445-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="cc445-110">ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE: このメソッドが返す `ICorDebugTypeEnum` に含まれる型パラメーターの数は、対応するクラスの仮型パラメーターの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cc445-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="cc445-111">たとえば、型が `class Dict<String,int32>`の場合、`EnumerateTypeParameters` は `String` および `int32` を表すオブジェクトを順番に含む `ICorDebugTypeEnum` を返します。</span><span class="sxs-lookup"><span data-stu-id="cc445-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="cc445-112">ELEMENT_TYPE_FNPTR: `ICorDebugTypeEnum` に含まれる型パラメーターの数は、関数で許容される引数の数より1大きくなります。</span><span class="sxs-lookup"><span data-stu-id="cc445-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="cc445-113">`ICorDebugTypeEnum` に格納されている最初の型パラメーターは、関数の戻り値の型であり、後続の型パラメーターは関数のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="cc445-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="cc445-114">ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF、または ELEMENT_TYPE_PTR: 1 つの型パラメーターが返されます。</span><span class="sxs-lookup"><span data-stu-id="cc445-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="cc445-115">たとえば、型が `int32[]`などの配列型である場合、`EnumerateTypeParameters` は `int32`を表すオブジェクトを含む `ICorDebugTypeEnum` を返します。</span><span class="sxs-lookup"><span data-stu-id="cc445-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc445-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="cc445-116">Requirements</span></span>  
 <span data-ttu-id="cc445-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc445-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc445-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc445-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc445-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc445-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc445-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc445-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

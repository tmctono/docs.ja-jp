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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8fa39a54437e60737aa052c495f58422bc0d3fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946238"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="287bf-102">ICorDebugType::EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="287bf-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="287bf-103">含む、ICorDebugTypeEnum インターフェイス ポインターを取得、<xref:System.Type>この ICorDebugType によって参照されるクラスのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="287bf-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="287bf-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="287bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="287bf-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="287bf-106">[out]アドレスへのポインター、`ICorDebugTypeEnum`型のパラメーターを格納しています。</span><span class="sxs-lookup"><span data-stu-id="287bf-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="287bf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="287bf-107">Remarks</span></span>  
 <span data-ttu-id="287bf-108">使用することができます`EnumerateTypeParameters`CorElementType 値がによって返される場合[icordebugtype::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS、ELEMENT_TYPE_VALUETYPE、ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF、ELEMENT_TYPE_PTR、または typ ELEMENT_TYPE_FNPTR します。</span><span class="sxs-lookup"><span data-stu-id="287bf-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="287bf-109">パラメーターとその順序の数は、種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="287bf-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="287bf-110">ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE:含まれる型パラメーターの数、`ICorDebugTypeEnum`このメソッドが返すし、対応するクラスの仮引数の型パラメーターの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="287bf-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="287bf-111">たとえば、次の種類は`class Dict<String,int32>`、し`EnumerateTypeParameters`が返されます、`ICorDebugTypeEnum`を表すオブジェクトを格納している`String`と`int32`シーケンスでします。</span><span class="sxs-lookup"><span data-stu-id="287bf-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="287bf-112">TYP ELEMENT_TYPE_FNPTR:含まれる型パラメーターの数、`ICorDebugTypeEnum`はいずれかに、関数が受け取る引数の数を超えています。</span><span class="sxs-lookup"><span data-stu-id="287bf-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="287bf-113">含まれる最初の型パラメーター、`ICorDebugTypeEnum`関数の戻り値の型であり、その後の型パラメーターは関数のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="287bf-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="287bf-114">ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF、または ELEMENT_TYPE_PTR:1 つの型パラメーターが返されます。</span><span class="sxs-lookup"><span data-stu-id="287bf-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="287bf-115">たとえば、型が配列型などに設定されている場合`int32[]`、`EnumerateTypeParameters`が返されます、`ICorDebugTypeEnum`表すオブジェクトを格納している`int32`します。</span><span class="sxs-lookup"><span data-stu-id="287bf-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="287bf-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="287bf-116">Requirements</span></span>  
 <span data-ttu-id="287bf-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="287bf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="287bf-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="287bf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="287bf-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="287bf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="287bf-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="287bf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

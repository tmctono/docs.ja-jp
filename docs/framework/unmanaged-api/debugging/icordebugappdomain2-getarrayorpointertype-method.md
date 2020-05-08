---
title: ICorDebugAppDomain2::GetArrayOrPointerType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: bbf43f3936823b9a8e562cb32cfa2eef08840033
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895185"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="c2a44-102">ICorDebugAppDomain2::GetArrayOrPointerType メソッド</span><span class="sxs-lookup"><span data-stu-id="c2a44-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="c2a44-103">指定した型、または指定した型へのポインターまたは参照の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2a44-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a44-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2a44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a44-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2a44-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="c2a44-106">から作成する基になるネイティブ型 (配列、ポインター、または参照) を指定する CorElementType 列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="c2a44-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="c2a44-107">から配列のランク (次元の数)。</span><span class="sxs-lookup"><span data-stu-id="c2a44-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="c2a44-108">がポインターまたは参照型`elementType`を指定する場合、この値は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a44-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="c2a44-109">から作成される配列、ポインター、または参照の型を表す、の型のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c2a44-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c2a44-110">入出力構築された配列、ポインター `ICorDebugType`型、または参照型を表すオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c2a44-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a44-111">解説</span><span class="sxs-lookup"><span data-stu-id="c2a44-111">Remarks</span></span>  
 <span data-ttu-id="c2a44-112">*ElementType*の値には、次のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a44-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="c2a44-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="c2a44-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="c2a44-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="c2a44-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="c2a44-115">ELEMENT_TYPE_ARRAY または ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="c2a44-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="c2a44-116">*ElementType*の値が ELEMENT_TYPE_PTR または ELEMENT_TYPE_BYREF の場合、 *n ランク*は0にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a44-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a44-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2a44-117">Requirements</span></span>  
 <span data-ttu-id="c2a44-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2a44-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a44-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2a44-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2a44-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a44-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a44-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a44-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

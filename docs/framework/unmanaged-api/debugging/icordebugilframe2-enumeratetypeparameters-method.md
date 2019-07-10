---
title: ICorDebugILFrame2::EnumerateTypeParameters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2e53bfb46579cc51b7ad88ef7de2b9f8d2f9390
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758758"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="d761b-102">ICorDebugILFrame2::EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="d761b-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="d761b-103">含む ICorDebugTypeEnum オブジェクトを取得、<xref:System.Type>このフレーム内のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="d761b-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d761b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d761b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d761b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d761b-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="d761b-106">型パラメーターの列挙を許可する ICorDebugTypeEnum インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d761b-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="d761b-107">型パラメーターの一覧には、メソッドの型パラメーター (ある場合) 後にクラス型パラメーター (ある場合) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d761b-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d761b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d761b-108">Remarks</span></span>  
 <span data-ttu-id="d761b-109">使用して、 [imetadataimport 2::enumgenericparams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)をクラスの型パラメーターとメソッドの数の入力パラメーターがこの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d761b-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="d761b-110">型パラメーターは、常に使用できません。</span><span class="sxs-lookup"><span data-stu-id="d761b-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d761b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d761b-111">Requirements</span></span>  
 <span data-ttu-id="d761b-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d761b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d761b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d761b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d761b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d761b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d761b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d761b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

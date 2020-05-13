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
ms.openlocfilehash: 9020fed83b1c57cae3cc492872a279afb0195983
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205167"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="e5910-102">ICorDebugILFrame2::EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="e5910-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="e5910-103">このフレームのパラメーターを格納している、テキスト型の型の列挙体オブジェクトを取得し <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="e5910-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5910-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5910-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5910-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5910-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="e5910-106">型パラメーターの列挙を可能にする、テキスト型のインターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5910-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="e5910-107">型パラメーターの一覧には、クラス型パラメーター (存在する場合) と、その後にメソッド型パラメーター (存在する場合) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5910-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5910-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5910-108">Remarks</span></span>  
 <span data-ttu-id="e5910-109">[IMetaDataImport2:: EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md)メソッドを使用して、このリストに含まれるクラス型パラメーターとメソッド型パラメーターの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5910-109">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="e5910-110">型パラメーターは常に使用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e5910-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5910-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5910-111">Requirements</span></span>  
 <span data-ttu-id="e5910-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5910-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5910-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5910-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5910-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5910-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5910-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5910-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

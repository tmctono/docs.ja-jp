---
title: ICorDebugModule::GetClassFromToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6da6fabc6632bea58b28a00f55d05f4c2cc5b46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762672"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="ebf02-102">ICorDebugModule::GetClassFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="ebf02-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="ebf02-103">メタデータ トークンで指定されたクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ebf02-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf02-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebf02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf02-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebf02-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="ebf02-106">[in]`mdTypeDef`クラスのメタデータを参照するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="ebf02-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="ebf02-107">[out]クラスを表す ICorDebugClass オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ebf02-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf02-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ebf02-108">Requirements</span></span>  
 <span data-ttu-id="ebf02-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf02-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf02-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebf02-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebf02-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebf02-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebf02-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf02-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: ICorDebugType::GetBase メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: cff527aa7cde6a13667d47d030a0ef7db96ad5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122346"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="3d524-102">ICorDebugType::GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="3d524-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="3d524-103">この `ICorDebugType`によって表される型の基本型 (存在する場合) を表す、テキスト型へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d524-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d524-104">構文</span><span class="sxs-lookup"><span data-stu-id="3d524-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d524-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3d524-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="3d524-106">入出力基本型を表す `ICorDebugType` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3d524-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d524-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d524-107">Remarks</span></span>  
 <span data-ttu-id="3d524-108">型の基本型を検索すると、オブジェクトまたはその親クラスのすべてのフィールドを出力するなど、一般的なデバッガー機能を実装するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="3d524-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d524-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="3d524-109">Requirements</span></span>  
 <span data-ttu-id="3d524-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d524-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d524-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d524-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d524-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d524-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d524-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d524-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
